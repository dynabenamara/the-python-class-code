# the-python-class-code
  import os
import shutil

# File to ignore
main_file = 'code for the python class.py'

# Directory paths
downloads = r'C:\Users\Delllll\Downloads'
documents_folder =os.path.join(downloads, 'documents')
audio_folder = os.path.join(downloads, 'audio')
pictures_folder = os.path.join(downloads, 'pictures')
videos_folder = os.path.join(downloads, 'videos')
programming_folder = os.path.join(downloads, 'programming')

# File format lists
doc_file_formats = ['pdf', 'doc', 'txt', 'rtf', 'odt', 'html', 'xls', 'ppt', 'csv']
audio_file_formats = ['mp3', 'wav', 'wma', 'aac', 'flac', 'ogg', 'aiff','jfif','.jpg']
picture_file_formats = ['jpeg', 'png', 'gif', 'bmp', 'tiff', 'raw']
videos_file_formats = ['mp4', 'avi', 'mov', 'wmv', 'flv', 'mkv', 'mpg', 'm4v', 'webm', '3gp']
programming_file_formats = ['.c', '.cpp', '.java', '.py', '.rb', '.js']

# Get list of files in downloads directory
files = os.listdir(downloads)

# Ignore main file
if main_file in files:
    files.remove(main_file)

# Move files to appropriate folders based on file format
for file in files:
    file_ext = file.split('.')[-1].lower()
    if file_ext in doc_file_formats:
        src_file_path = os.path.join(downloads, file)
        if not os.path.exists(documents_folder):
            os.mkdir(documents_folder)
        dst_file_path = os.path.join(documents_folder, file)
        if not os.path.exists(dst_file_path):
            shutil.move(src_file_path, dst_file_path)
    elif file_ext in audio_file_formats:
        src_file_path = os.path.join(downloads, file)
        if not os.path.exists(audio_folder):
            os.mkdir(audio_folder)
        dst_file_path = os.path.join(audio_folder, file)
        if not os.path.exists(dst_file_path):
            shutil.move(src_file_path, dst_file_path)
    elif file_ext in picture_file_formats:
        src_file_path = os.path.join(downloads, file)
        if not os.path.exists(pictures_folder):
            os.mkdir(pictures_folder)
        dst_file_path = os.path.join(pictures_folder, file)
        if not os.path.exists(dst_file_path):
            shutil.move(src_file_path, dst_file_path)
    elif file_ext in videos_file_formats:
        src_file_path = os.path.join(downloads, file)
        if not os.path.exists(videos_folder):
            os.mkdir(videos_folder)
        dst_file_path = os.path.join(videos_folder, file)
        if not os.path.exists(dst_file_path):
            shutil.move(src_file_path, dst_file_path)
    elif file_ext in programming_file_formats:
        src_file_path = os.path.join(downloads, file)
        if not os.path.exists(programming_folder):
            os.mkdir(programming_folder)
        dst_file_path = os.path.join(programming_folder, file)
        if not os.path.exists(dst_file_path):
            shutil.move(src_file_path, dst_file_path)
