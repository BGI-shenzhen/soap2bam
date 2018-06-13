# soap2bam
<b>soap2bam: A efficient software tools to convert soap to bam/sam format</b>
</br></br></br></br>
The newest version of this funtion was integrated into toolkit <b>[BamDeal](https://github.com/BGI-shenzhen/BamDeal) </b>,please replace soap2bam by this <b>[BamDeal](https://github.com/BGI-shenzhen/BamDeal)</b>.

```php
           ./BamDeal    convert    soap2bam
```

</br></br>

1) Install
------------

Please replace soap2bam with this toolkit <b>[BamDeal](https://github.com/BGI-shenzhen/BamDeal)</b>.

</br></br></br>

  This software rely htslib，so should Pre-install htslib first [samtools-1.5/htslib-1.5](https://sourceforge.net/projects/samtools/files/samtools)
  </br>Then Just  [make]  or [sh  make.sh ]  to compile this software.
  </br>the final software can be found in the Dir [bin/soap2bam]

 For <b>linux /Unix </b>
<pre>
        tar -zxvf  soap2bam-XXX.tar.gz
        cd soap2bam-XXX;                             # if Link do not work ,Try <b>re-install</b> two library
        cd src;                                      #【zlib and htslib】 and copy them to the library Dir
        make ; make clean                            # soap2bam-XX/src/include/zlib 
        ../bin/soap2bam                              
</pre>
</br>

For <b>macOS </b>
<pre>
#step1 :Should must <b>re-install</b>  third  library 【zlib and gzstream htslib】
              see  [zlib and gzstream] website 
#step2  :  # Copy these two library into Dirs 
              cp libz.a libz.so*  soap2bam-XX/src/include/zlib
              cp libgzstream.a  soap2bam-XX/src/include/gzstream
#step3  : 
              sh make.sh # or [make && make clean]
</pre>

2) Example
------------
* 1) soap2sam
```
#To convert soap file to the sam file

     ./bin/soap2bam   -InSoap in.soap  -OutSam out.sam.gz
     ./bin/soap2bam   -InSoap in.soap  -OutSam  out.sam.gz -Dict  Ref.dict
     ./bin/soap2bam   -InSoap in.soap.gz -OutSam  out.sam.gz  -Dict Ref.fa

   1. Soap2bam -i <in.soap> -s AAA
      This will convert the SOAP to SAM and output to a compressed file named AAA in current directory

   2. Soap2bam -i <in.soap> -b AAA -d Ref.fa
      This will convert the SOAP to BAM with the header from reference FASTA and output to a compressed file named AAA in current directory.

```

* 2) soap2bam
```
# To convert soap file to the bam file

     ./bin/soap2bam    -InSoap in.soap  -Outbam out.bam  -Dict  Ref.fa
  # Also you the  add the  -ShiftQ  modify the seqQ  for ASCII64 --> ASCII33
     ./bin/soap2bam    -InSoap in.soap  -Outbam out.bam  -Dict  Ref.fa -ShiftQ -31

```

3) Introduction
------------

* <b> Parameter description</b>

```php

./BamDeal    convert  soap2bam

        Usage: soap2bam  -i <in.soap> -s <out.sam>
        Usage: soap2bam  -i <in.soap> -b <out.bam> -d Ref.dict

                -i   <str>   input  Soap file
                -b   <str>   output BAM file
                -s   <str>   output SAM file

                -d   <str>   input ref FASTA to get header for BAM
                -p           if soap is PairOut,for flag
                -Q   <int>   shift sequence quality score by [+31] or [-31] or [0], default [0]
                -g           all read in memory to search mate information

                -h           show more help [hewm2008 v1.04]


```

4) Results
------------
Format Introduction

* [soap format](http://soap.genomics.org.cn/soapaligner.html)
  </br> [chinese soap introduction](http://blog.sina.com.cn/s/blog_70b2b6020101b609.html)
* [sam bam format](https://samtools.github.io/hts-specs/SAMv1.pdf)

5）Discussing
------------
- email: hewm2008@gmail.com / hewm2008@qq.com  
- join the<b><i> QQ Group : 125293663</b></i>



######################swimming in the sky and flying in the sea ########################### ##
