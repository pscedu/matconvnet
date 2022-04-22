# MatConvNet: CNNs for MATLAB

**MatConvNet** is a MATLAB toolbox implementing *Convolutional Neural
Networks* (CNNs) for computer vision applications. It is simple,
efficient, and can run and learn state-of-the-art CNNs. Several
example CNNs are included to classify and encode images. Please visit
the [homepage](http://www.vlfeat.org/matconvnet) to know more.

In case of compilation issues, please read first the
[Installation](http://www.vlfeat.org/matconvnet/install/) and
[FAQ](http://www.vlfeat.org/matconvnet/faq/) section before creating an GitHub
issue. For general inquiries regarding network design and training
related questions, please use the
[Discussion forum](https://groups.google.com/d/forum/matconvnet).

## Compiling on Bridges-2
Last Update: April 22, 2022

1. Start an interactive session. Note: if you want to have GPU and test it, you need to both load CUDA and request a GPU.
```
interact -gpu -n 5 --mem=11Gb
```

2. Load the appropriate modules
```
module load matlab/R2021a
module load cuda/11.1.1
```

3. Clone repo
```
git clone git@github.com:vlfeat/matconvnet.git
```

4. Edit `Makefile` file
Inside the matconvnet folder you will see a file named `Makefile`. Change line 27 from

```
CUDAROOT ?= /usr/local/cuda
```

to

```
CUDAROOT ?= /jet/packages/spack/opt/spack/linux-centos8-zen/gcc-8.3.1/cuda-11.1.1-a6ajxenobex5bvpejykhtnfut4arfpwh
```

6. Change directories to the folder where the file `Makefile` lives and run the command

```
make
```

it might take several minutes to compile. Be patient.

7. Start Matlab to confirm it compiled and works properly. Following the instructions in this package

```
matlab -nodesktop -nosplash

MATLAB is selecting SOFTWARE OPENGL rendering.

                                                                < M A T L A B (R) >
                                                      Copyright 1984-2021 The MathWorks, Inc.
                                                 R2021a Update 1 (9.10.0.1649659) 64-bit (glnxa64)
                                                                   April 13, 2021

 
To get started, type doc.
For product information, visit www.mathworks.com.
 
>> run matlab/vl_setupnn.m
>> vl_testnn

 Running nnbilinearsampler
  Setting up nnbilinearsampler[dataType=single,device=cpu]
  Done setting up nnbilinearsampler[dataType=single,device=cpu] in 0.000941 seconds
   Running nnbilinearsampler[dataType=single,device=cpu]/check_der_x(ih=value1,iw=value1,oh=value1,ow=value1,multiple_grids=value1)
   Done nnbilinearsampler[dataType=single,device=cpu]/check_der_x(ih=value1,iw=value1,oh=value1,ow=value1,multiple_grids=value1) in 0.67398 seconds
   Running nnbilinearsampler[dataType=single,device=cpu]/check_der_x(ih=value1,iw=value1,oh=value1,ow=value1,multiple_grids=value2)
   Done nnbilinearsampler[dataType=single,device=cpu]/check_der_x(ih=value1,iw=value1,oh=value1,ow=value1,multiple_grids=value2) in 0.076365 seconds
   Running nnbilinearsampler[dataType=single,device=cpu]/check_der_x(ih=value1,iw=value1,oh=value1,ow=value2,multiple_grids=value1)
   Done nnbilinearsampler[dataType=single,device=cpu]/check_der_x(ih=value1,iw=value1,oh=value1,ow=value2,multiple_grids=value1) in 0.077341 seconds
   Running nnbilinearsampler[dataType=single,device=cpu]/check_der_x(ih=value1,iw=value1,oh=value1,ow=value2,multiple_grids=value2)
   Done nnbilinearsampler[dataType=single,device=cpu]/check_der_x(ih=value1,iw=value1,oh=value1,ow=value2,multiple_grids=value2) in 0.061363 seconds
   Running nnbilinearsampler[dataType=single,device=cpu]/check_der_x(ih=value1,iw=value2,oh=value1,ow=value1,multiple_grids=value1)
   Done nnbilinearsampler[dataType=single,device=cpu]/check_der_x(ih=value1,iw=value2,oh=value1,ow=value1,multiple_grids=value1) in 0.093338 seconds
   Running nnbilinearsampler[dataType=single,device=cpu]/check_der_x(ih=value1,iw=value2,oh=value1,ow=value1,multiple_grids=value2)
   Done nnbilinearsampler[dataType=single,device=cpu]/check_der_x(ih=value1,iw=value2,oh=value1,ow=value1,multiple_grids=value2) in 0.036754 seconds
   Running nnbilinearsampler[dataType=single,device=cpu]/check_der_x(ih=value1,iw=value2,oh=value1,ow=value2,multiple_grids=value1)
   Done nnbilinearsampler[dataType=single,device=cpu]/check_der_x(ih=value1,iw=value2,oh=value1,ow=value2,multiple_grids=value1) in 0.034694 seconds
   Running nnbilinearsampler[dataType=single,device=cpu]/check_der_x(ih=value1,iw=value2,oh=value1,ow=value2,multiple_grids=value2)
   Done nnbilinearsampler[dataType=single,device=cpu]/check_der_x(ih=value1,iw=value2,oh=value1,ow=value2,multiple_grids=value2) in 0.039541 seconds
   Running nnbilinearsampler[dataType=single,device=cpu]/check_der_x(ih=value1,iw=value3,oh=value1,ow=value1,multiple_grids=value1)
   Done nnbilinearsampler[dataType=single,device=cpu]/check_der_x(ih=value1,iw=value3,oh=value1,ow=value1,multiple_grids=value1) in 0.030887 seconds
   Running nnbilinearsampler[dataType=single,device=cpu]/check_der_x(ih=value1,iw=value3,oh=value1,ow=value1,multiple_grids=value2)
   Done nnbilinearsampler[dataType=single,device=cpu]/check_der_x(ih=value1,iw=value3,oh=value1,ow=value1,multiple_grids=value2) in 0.036112 seconds
   Running nnbilinearsampler[dataType=single,device=cpu]/check_der_x(ih=value1,iw=value3,oh=value1,ow=value2,multiple_grids=value1)
.... (suppressing most of the output)
```

The tests will take several minutes as well. Be patient.
