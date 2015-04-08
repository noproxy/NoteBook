#FFMPEG command line option



```
-r rate             set frame rate (Hz value, fraction or abbreviation)
-s size             set frame size (WxH or abbreviation)
-aspect aspect      set aspect ratio (4:3, 16:9 or 1.3333, 1.7777)
-fixaspect          fix aspect ratio
-croptop size       set top crop band size (in pixels)
-cropbottom size    set bottom crop band size (in pixels)
-cropleft size      set left crop band size (in pixels)
-cropright size     set right crop band size (in pixels)
-padtop size        set top pad band size (in pixels)
-padbottom size     set bottom pad band size (in pixels)
-padleft size       set left pad band size (in pixels)
-padright size      set right pad band size (in pixels)
-padcolor color     set color of pad bands (Hex 000000 thru FFFFFF)
-vn                 disable video
-bt tolerance       set video bitrate tolerance (in kbit/s)
-maxrate bitrate    set max video bitrate tolerance (in kbit/s)
-minrate bitrate    set min video bitrate tolerance (in kbit/s)
-bufsize size       set ratecontrol buffer size (in kByte)
-vcodec codec       force video codec ('copy' to copy stream)
-sameq              use same video quality as source (implies VBR)
-pass n             select the pass number (1 or 2)
-passlogfile file   select two pass log file name
-newvideo           add a new video stream to the current output stream

Advanced Video options:
-pix_fmt format     set pixel format
-g gop_size         set the group of picture size
-intra              use only intra frames
-vdt n              discard threshold
-qscale q           use fixed video quantiser scale (VBR)
-qmin q             min video quantiser scale (VBR)
-qmax q             max video quantiser scale (VBR)
-lmin lambda        min video lagrange factor (VBR)
-lmax lambda        max video lagrange factor (VBR)
-mblmin q           min macroblock quantiser scale (VBR)
-mblmax q           max macroblock quantiser scale (VBR)
-qdiff q            max difference between the quantiser scale (VBR)
-qblur blur         video quantiser scale blur (VBR)
-qsquish squish     how to keep quantiser between qmin and qmax (0 = clip, 1 = use differentiable function)
-qcomp compression  video quantiser scale compression (VBR)
-rc_init_cplx complexity  initial complexity for 1-pass encoding
-b_qfactor factor   qp factor between p and b frames
-i_qfactor factor   qp factor between p and i frames
-b_qoffset offset   qp offset between p and b frames
-i_qoffset offset   qp offset between p and i frames
-ibias bias         intra quant bias
-pbias bias         inter quant bias
-rc_eq equation     set rate control equation
-rc_override override  rate control override for specific intervals
-me method          set motion estimation method
-dct_algo algo      set dct algo
-idct_algo algo     set idct algo
-me_threshold       motion estimaton threshold
-mb_threshold       macroblock threshold
-er n               set error resilience
-ec bit_mask        set error concealment
-bf frames          use 'frames' B frames
-mbd mode           macroblock decision
-mbcmp cmp function  macroblock compare function
-ildctcmp cmp function  ildct compare function
-subcmp cmp function  subpel compare function
-cmp cmp function   fullpel compare function
-precmp cmp function  pre motion estimation compare function
-preme              pre motion estimation
-lelim elim         single coefficient elimination threshold for luminance (negative values also consider DC coefficient)
-celim elim         single coefficient elimination threshold for chrominance (negative values also consider DC coefficient)
-lumi_mask          luminance masking
-dark_mask          darkness masking
-scplx_mask         spatial complexity masking
-tcplx_mask         temporal complexity masking
-p_mask             inter masking
-4mv                use four motion vector by macroblock (MPEG4)
-obmc               use overlapped block motion compensation (h263+)
-lf                 use loop filter (h263+)
-part               use data partitioning (MPEG4)
-bug param          workaround not auto detected encoder bugs
-strict strictness  how strictly to follow the standards
-deinterlace        deinterlace pictures
-ildct              force interlaced dct support in encoder (MPEG2/MPEG4)
-ilme               force interlaced me support in encoder (MPEG2/MPEG4)
-psnr               calculate PSNR of compressed frames
-vstats             dump video coding statistics to file
-vhook module       insert video processing module
-aic                enable Advanced intra coding (h263+)
-aiv                enable Alternative inter vlc (h263+)
-umv                enable Unlimited Motion Vector (h263+)
-ssm                enable Slice Structured mode (h263+)
-alt                enable alternate scantable (MPEG2/MPEG4)
-qprd               
-cbp                
-trell              enable trellis quantization
-mv0                try to encode each MB with MV=<0,0> and choose the better one (has no effect if mbd=0)
-naq                normalize adaptive quantization
-cgop               closed gop
-sgop               strict gop
-noout              skip bitstream encoding
-scan_offset        enable SVCD Scan Offset placeholder
-qpel               enable 1/4-pel
-intra_matrix matrix  specify intra matrix coeffs
-inter_matrix matrix  specify inter matrix coeffs
-top                top=1/bottom=0/auto=-1 field first
-nr                 noise reduction
-qns                quantization noise shaping
-sc_threshold threshold  scene change threshold
-me_range range     limit motion vectors range (1023 for DivX player)
-dc precision       intra_dc_precision
-coder              coder type
-context            context model
-pred               prediction method
-vprofile           profile
-vlevel             level
-nssew              weight
-subq               
-mepc factor (1.0 = 256)  motion estimation bitrate penalty compensation
-lowres             
-vtag fourcc/tag    force video tag/fourcc
-skip_threshold threshold  frame skip threshold
-skip_factor factor  frame skip factor
-skip_exp exponent  frame skip exponent
-skip_cmp compare function  frame skip compare function
-gray               encode/decode grayscale

Audio options:
-aframes number     set the number of audio frames to record
-ab bitrate         set audio bitrate (in kbit/s)
-ar rate            set audio sampling rate (in Hz)
-ac channels        set number of audio channels
-an                 disable audio
-acodec codec       force audio codec ('copy' to copy stream)
-vol volume         change audio volume (256=normal)
-newaudio           add a new audio stream to the current output stream
-alang code         set the ISO 639 language code (3 letters) of the current audio stream

Advanced Audio options:
-atag fourcc/tag    force audio tag/fourcc

Subtitle options:
-scodec codec       force subtitle codec ('copy' to copy stream)
-newsubtitle        add a new subtitle stream to the current output stream
-slang code         set the ISO 639 language code (3 letters) of the current subtitle stream

Audio/Video grab options:
-vd device          set video grab device
-vc channel         set video grab channel (DV1394 only)
-tvstd standard     set television standard (NTSC, PAL (SECAM))
-ad device          set audio device
-grab format        request grabbing using
-gd device          set grab device

Advanced options:
-map file:stream[:syncfile:syncstream]  set input stream mapping
-map_meta_data outfile:infile  set meta data information of outfile from infile
-debug              print specific debug info
-vismv              visualize motion vectors
-benchmark          add timings for benchmarking
-dump               dump each input packet
-hex                when dumping packets, also dump the payload
-bitexact           only use bit exact algorithms (for codec testing)
-re                 read input at native frame rate
-loop               loop (current only works with images)
-loop_output        number of times to loop output in formats that support looping (0 loops forever)
-threads count      thread count
-vsync              video sync method
-async              audio sync method
-vglobal            video global header storage type
-copyts             copy timestamps
-shortest           finish encoding within shortest input
-b_strategy strategy  dynamic b frame selection strategy
-ps size            set packet size in bits
-error rate         error rate
-muxrate rate       set mux rate
-packetsize size    set packet size
-muxdelay seconds   set the maximum demux-decode delay
-muxpreload seconds  set the initial demux-decode delay
-muxab bitrate      set the audio bitrate in mux tag (in kbit/s)
-muxvb bitrate      set the video bitrate in mux tag (in kbit/s)
```
##codecs\file
```ffmpeg -formats```  


Reference
- [myce.com](http://club.myce.com/f62/ffmpeg-command-line-options-166608)