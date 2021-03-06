Patches here

   * [remove-unneeded-qt-define][] Removes a `-DQT_WEBKIT` which looks like
     it is a left-over from some older version (it is never used anywhere in
     the SDK).

   * [fix-compile-warnings][] Fix some compilation warnings
       - integers casted to void* are too small for int64. Type 'long' is
        guaranteed to fit.
       - 'int' offsets casted to void* should be size_t
       - Check #ifndef before defining things twice (GL_GLEXT_PROTOTYPES).
       - Assign compile time string constants to 'const char *' instead of
        'char *'.

   * [add-make-install][] Adds a 'make install' target to the Makefile.
     It is very annoying if the library is somewhere in some source-tree
     instead in the system just to use in software.
     It puts	     
     the library into `/usr/local/lib/libovr.a` and the includes in
     `/usr/local/include/ovr`. In applications, programs can include
     `#include <ovr/OVR.h>` now. Anywhere, without pointing to the SDK
     sourcetree somewhere.
     
   * [fix-indentation-mess-in-samples][] The files in the samples directory
     are indented typically with 4 spaces, with some stray tabs in-between.
     Since tabs don't have a standard indentation (common are 2, 4 and 8
     depending on preference), this looks very messy in any editor that is not
     set to 4. Fixed these to be always 4 spaces.

[add-make-install]: https://github.com/hzeller/oculus-sdk-patches/raw/master/0.2.5/add-make-install.patch
[fix-compile-warnings]: https://github.com/hzeller/oculus-sdk-patches/raw/master/0.2.5/fix-compile-warnings.patch
[fix-indentation-mess-in-samples]: https://github.com/hzeller/oculus-sdk-patches/raw/master/0.2.5/fix-indentation-mess-in-samples.patch
[remove-unneeded-qt-define]: https://github.com/hzeller/oculus-sdk-patches/raw/master/0.2.5/remove-unneeded-qt-define.patch
