# TRTC SDK

_[简体中文](README-zh_CN.md) | English_
## Overview

Leveraging Tencent's many years of experience in network and audio/video technologies, Tencent Real-Time Communication (TRTC) offers solutions for group audio/video calls and low-latency interactive live streaming. With TRTC, you can quickly develop cost-effective, low-latency, and high-quality interactive audio/video services. [Learn more](https://www.tencentcloud.com/document/product/647/35078).

> We offer SDKs for web, Android, iOS, macOS, Windows, Flutter, WeChat Mini Program, and [other mainstream platforms](https://github.com/LiteAVSDK?q=TRTC_&type=all&sort=).



## Changelog
### Version 11.5 @ 2023.11.27

#### Improvements
- All platforms: Optimized the performance and stability of the video engine.

- All platforms: Optimized the stability of the audio engine.

- All platforms: Optimized the behavior strategy of some APIs, see the adjustment of interface behavior for details.

- All platforms: Optimized the strategy and performance of the background music module (BGM module), reducing the occurrence of BGM playback exceptions.

- Windows: Optimized HEVC hardware decoding compatibility with AMD and Nvidia graphics cards.

- Windows: Optimized the overall performance of screen sharing, improved screen capture frame rate and stability.

- Android: Optimized the playback effect of TRTC with VODPlayer.

- iOS & Mac: Optimized the performance of pre-processing and rendering using Metal.


#### Adjustment of Interface Behavior
- All platforms: When the video resolution is set to vertical 540P (expecting 540x960), the specific resolution for processing is adjusted from 544x960 to 536x960.

- All platforms: The callback interval of BGM progress callback `onPlayProgress` is adjusted from 200ms to 300ms.

- All platforms: The internal implementation of the BGM module is adjusted to a singleton, and the musicID needs to be globally unique in multiple instances. When developers use sub-instances to play BGM, please make sure that different instances use different musicIDs.

- All platforms: Local recording event status codes are adjusted to be returned asynchronously. The default return is 0 after the related interface is called, and the specific status code is obtained through the corresponding event callback.

- All platforms: Adjust the following status codes for the `onLocalRecordBegin` callback for starting recording events.

<table>
<tr>
<td rowspan="1" colSpan="1" >Event</td>

<td rowspan="1" colSpan="1" >Status code before v11.5	</td>

<td rowspan="1" colSpan="1" >Status code in v11.5</td>
</tr>

<tr>
<td rowspan="1" colSpan="1" >Recording has started, stop previous recording first</td>

<td rowspan="1" colSpan="1" >-1</td>

<td rowspan="1" colSpan="1" >-6</td>
</tr>

<tr>
<td rowspan="1" colSpan="1" >Directory has no write permission, please check directory permissions</td>

<td rowspan="1" colSpan="1" >-2</td>

<td rowspan="1" colSpan="1" >-8</td>
</tr>

<tr>
<td rowspan="1" colSpan="1" >Incorrect file extension (e.g. unsupported recording format)	</td>

<td rowspan="1" colSpan="1" >-3</td>

<td rowspan="1" colSpan="1" >-2</td>
</tr>
</table>

- iOS & Android: Optimized the continuity of mobile screen sharing, retaining the last frame sent during sharing pause, with a frame rate of 1-2 fps.

- iOS & Android: Adjusted the response behavior of gravity sensor, only responding to gravity sensor on or off.


For the release notes of earlier versions, click [More](https://www.tencentcloud.com/document/product/647/39426).


## Contact Us
- If you have questions, see [FAQs](https://www.tencentcloud.com/document/product/647/36057).

- To learn about how the TRTC SDK can be used in different scenarios, see [Sample Code](https://www.tencentcloud.com/document/product/647/42963).

- For complete API documentation, see [SDK API Documentation](https://www.tencentcloud.com/document/product/647/35119).

- Communication & Feedback   
Welcome to join our Telegram Group to communicate with our professional engineers! We are more than happy to hear from you~
Click to join: [https://t.me/+EPk6TMZEZMM5OGY1](https://t.me/+EPk6TMZEZMM5OGY1)   
Or scan the QR code   
  <img src="https://qcloudimg.tencent-cloud.cn/raw/79cbfd13877704ff6e17f30de09002dd.jpg" width="300px">    

>**Notice:** 
> OCDemo and SwiftDemo only support MacOS 13.0 and above.
