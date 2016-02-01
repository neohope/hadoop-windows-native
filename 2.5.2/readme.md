# About#
hadoop-2.5.2 windows native dll and exe

# What to do #
1. download the right version of binary files from bin/
2. scan winutils.exe if you want
3. try to run winutils.exe, if it does not work, you need vcredist from M$.(VS2010 or VS2013U5)
4. copy the binary files to %HADOOP_HOME%\bin
5. have fun

# How to build #
1. set JAVA_HOME to your JDK path
2. build winutils.sln
3. build native.sln
4. go to bin to find the files you need

# How to generate the JNI header files? #
The native.sln needs some JNI headers to build, which are already included in the native project. Just in case you want to know how to genertate therese files:
	
	unzip hadoop-common-2.5.1.jar
	javah org.apache.hadoop.util.NativeCrc32
	javah org.apache.hadoop.io.compress.lz4.Lz4Compressor
	javah org.apache.hadoop.io.compress.lz4.Lz4Decompressor
	javah org.apache.hadoop.io.nativeio.NativeIO
	javah org.apache.hadoop.security.JniBasedUnixGroupsMapping
	javah org.apache.hadoop.security.JniBasedUnixGroupsMapping

# Any difference? #
1. copy from hadoop-2.5.2-src\hadoop-common-project\hadoop-common\src\main\native
2. copy from hadoop-2.5.2-src\hadoop-common-project\hadoop-common\src\main\winutils
3. generate and add the javah header files
4. reconfig the out put path
5. reconfig the platform(Win32,x86) and config(Debug,Release) and out put path
