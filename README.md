# Apple-Media-Compression-Shortcuts

This repository hosts shortcuts for compressing photos and videos on Apple iPhone, iPad, and Mac devices, utilizing efficient formats and compression algorithms to significantly reduce file sizes while maintaining high visual fidelity.

## Features

- **Photo Conversion**: Converts JPEG images to HEIF format, achieving size reductions to 15-50% of the original without noticeable quality loss on a 34-inch display.
- **Video Compression**: Compresses videos using `ffmpeg`, targeting size reductions to 15-50% of the original. While paused on a 34-inch display, a minimal quality difference may be perceptible.

## Prerequisites

- Ensure your device has the original photos; you might need to download originals from iCloud, which could consume significant data bandwidth.
- Photo conversion and video compression processes can be time-consuming. Start with a small test album.
- Lower-spec computers may take a considerable amount of time to compress videos.

## Safety Notice

To ensure data safety, these scripts do not include delete operations. Manual deletion of duplicate files is necessary. There are two ways to manage this:
1. For fewer files, directly import the converted files and let the system identify duplicates for deletion.
2. For batch processing, move files to a new album (e.g., "2022 photos"), run the script for this album, and post verification, delete the original photos before importing the converted ones.

## Batch Processing

For a large number of photos/videos, it is advisable to process in batches, such as yearly. Use the Photos app on your Mac to create yearly albums and batch-move files to these albums for organization.

## Photo Conversion (Compatible with iPhone/iPad)

Shortcut Link: [Convert Photos to HEIF](https://www.icloud.com/shortcuts/53321a7925b741acb9487b0ea6cb846f)

Before executing the downloaded shortcut, you must modify the input photo location. To preserve creation dates, which may be lost during conversion, use the [Actions](https://apps.apple.com/us/app/actions/id1586435171) app for iPhone/iPad. If you do not require the creation date, you may modify the script accordingly. The converted photos are stored in iCloud's "Downloads" folder.

## Video Compression (Compatible with Mac)

Shortcut Link: [Compress Videos with ffmpeg](https://www.icloud.com/shortcuts/149d07546ec34ecdad4a98b8abccc70d)

Before running the downloaded script, you need to set up `ffmpeg` by downloading it from [FFmpeg Official Download](https://ffmpeg.org/download.html) and placing the executable in the "Downloads" folder. Ensure its executability and test with a small video file using the command `ffmpeg -i input.mp4 output.mp4` in the terminal. The converted videos will be stored in the local "Downloads" folder.

To adjust quality, tweak the `-crf` parameter (default is 28). A lower value equates to higher quality; consider values like 25, 23, or 20. Note that even HEVC videos from iPhones can be significantly compressed, but avoid compressing already heavily compressed videos (like those from WeChat) as it may result in larger file sizes.

The default parameter `-c:v libx265` uses the CPU for compression, which is slower but provides good quality. You can switch to `-c:v hevc_videotoolbox`, which uses the GPU for compression, resulting in a significant speed boost. However, it may produce mosaic artifacts when dealing with fast-paced video transitions, so it's not recommended. When using hevc_videotoolbox, the parameter `-crf 28` doesn't have any effect, and you can only adjust the quality using `-b:v 2000k`.

## Disclaimer

These scripts are shared for educational and utility purposes. Please ensure you have backed up your data before using them. The author is not responsible for any data loss or corruption.



# 苹果iOS/iPad/Mac 照片和视频压缩快捷指令

本代码库提供了用于在苹果iPhone、iPad和Mac设备上压缩照片和视频的快捷指令，使用高效的格式和压缩算法显著减少文件大小，同时保持高视觉保真度。

## 特点

- **照片转换**：将JPEG图片转换为HEIF格式，可将文件大小压缩至原始大小的15-50%，在34英寸显示器上几乎看不出质量差异。
- **视频压缩**：使用`ffmpeg`压缩视频，目标是将文件大小压缩至原始大小的15-50%。在34英寸显示器上暂停时，可能会感觉到微小的质量差别。

## 前提条件

- 确保您的设备具有原始照片；您可能需要从iCloud下载原始文件，这可能会消耗大量数据带宽。
- 照片转换和视频压缩过程可能非常耗时。请先从一个小的测试相册开始。
- 低配置的计算机可能需要相当长的时间来压缩视频。

## 安全须知

为了确保数据安全，这些脚本不包含删除操作。需要手动删除重复文件。管理此操作的方法有两种：
1. 对于较少的文件，可以直接导入转换后的文件，并让系统识别重复文件以便删除。
2. 对于批量处理，将文件移至新相册（例如，“2022照片”），运行脚本，并在验证后删除原始照片，然后导入转换后的文件。

## 批量处理

对于大量照片/视频，建议分批处理，例如按年份。使用Mac上的照片应用程序创建年度相册，并将文件批量移动到这些相册中进行组织。（具体操作：打开Mac上的照片应用，点击搜索，然后输入“2022”，找到2022的所有照片，点击“查看全部”， 点击“筛选”，选择“照片”或者“视频”，按command+A全选文件，点击“添加到相簿”）

## 照片转换（与iPhone/iPad兼容）

快捷指令链接：[将照片转换为HEIF](https://www.icloud.com/shortcuts/53321a7925b741acb9487b0ea6cb846f)

在执行下载的快捷指令之前，必须修改输入照片的位置。为了保留可能在转换过程中丢失的创建日期，需要使用iPhone/iPad的[Actions](https://apps.apple.com/us/app/actions/id1586435171)应用程序。如果您不需要创建日期，可以相应修改脚本。转换后的照片存储在iCloud的“下载”文件夹中。

## 视频压缩（与Mac兼容）

快捷指令链接：[使用ffmpeg压缩视频](https://www.icloud.com/shortcuts/149d07546ec34ecdad4a98b8abccc70d)

在运行下载的脚本之前，您需要设置`ffmpeg`，通过[FFmpeg官方下载](https://ffmpeg.org/download.html)下载并将可执行文件放在“下载”文件夹中。确保其可执行性并使用命令`ffmpeg -i input.mp4 output.mp4`在终端中测试一个小视频文件。转换后的视频将存储在本地的“下载”文件夹中。

要调整质量，请调整`-crf`参数（默认值为28）。较低的值等于更高的质量；可以考虑使用25、23或20等值。请注意，即使是iPhone拍摄的HEVC视频也可以显著压缩，但避免压缩已经高度压缩的视频（如来自微信的视频），因为这可能导致文件大小增加。

默认参数 `-c:v libx265` 使用 CPU 进行压缩，速度较慢但提供良好的质量。您可以切换到 `-c:v hevc_videotoolbox`，它使用 GPU 进行压缩，会显著提高速度。然而，在处理快速视频转场时可能会产生马赛克伪影，因此不建议使用。当使用 `hevc_videotoolbox` 时，参数 `-crf 28` 不会产生任何效果，您只能通过 `-b:v 2000k` 来调整视频的质量。

## 免责声明

这些脚本仅用于教育和实用目的分享。在使用它们之前，请确保已备份数据。作者不对任何数据丢失或损坏负责。