require 'dotenv/load'
require 'iiif_s3'
require 'yaml'

TARGET_URL = 'https://mnyrop.github.io/peutinger-map-static'

task :build do 
    build_opts = {
        image_directory_name: "img",
        output_dir: "./docs",
        upload_to_s3: false,
        base_url: TARGET_URL,
        verbose: true
    }
    iiif = IiifS3::Builder.new build_opts
    iiif.create_build_directories

    file    = "./source/img/base.jpg"
    id      = File.basename(file, File.extname(file))

    obj = {
        "path" => "#{file}",
        "label" => "Peutinger Map Static",
        "description" => "TO DO",
        "attribution" => "TO DO",
        "id"       => id,
        "is_master" => true,
        "page_number" => 1,
        "is_document" => false
    }

    data = IiifS3::ImageRecord.new(obj)
    iiif.load data
    iiif.process_data
end