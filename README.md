split_file_into_three(r"D:\Backups\bigfile.7z")


import os

def split_file_into_three(input_file):
    file_size = os.path.getsize(input_file)
    part_size = file_size // 3
    remainder = file_size % 3

    print(f"Total size: {file_size} bytes")
    print(f"Each part size: ~{part_size} bytes")

    with open(input_file, 'rb') as f:
        for i in range(3):
            part_filename = f"{input_file}.part{i+1}"
            with open(part_filename, 'wb') as part_file:
                # Last file takes the remainder too
                bytes_to_write = part_size + (remainder if i == 2 else 0)
                part_file.write(f.read(bytes_to_write))
            print(f"Created: {part_filename}")

    print("✅ Splitting completed!")

# 👉 Change this to your 7z file path
split_file_into_three("large_archive.7z")
