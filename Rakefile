require 'dotenv/load'
require 'iiif_s3'

def add_image(file, is_doc = false)
    name = File.basename(file, File.extname(file))
    name_parts = name.split("_")
    is_paged = name_parts.length == 8
    page_num = is_paged ? name_parts[7].to_i : 1
    name_parts.pop if is_paged
    id = name_parts.join("_")

    obj = {
        "path" => "#{file}",
        "id"       => id,
        "label"    => name_parts.join("."),
        "is_master" => page_num == 1,
        "page_number" => page_num,
        "is_document" => false,
        "description" => "This is a test file generated as part of the development on the ruby IiifS3 Gem. <b> This should be bold.</b>"
    }

    if is_paged
        obj["section"] = "p#{page_num}"
        obj["section_label"] = "Page #{page_num}"
    end

    if is_doc
        obj["is_document"] = true
    end
    @data.push IiifS3::ImageRecord.new(obj)
end

task :build do 
    @opts = {
        image_directory_name: "img",
        output_dir: "./docs",
        upload_to_s3: false,
        base_url: 'https://mnyrop.github.io/peutinger-map-static',
        verbose: true
    }
 

    @data   = []
    @source = './source'

    iiif = IiifS3::Builder.new @opts
    iiif.create_build_directories

    Dir.glob("#{@source}/*") { |f| add_image(f) }

    iiif.load @data
    iiif.process_data
end