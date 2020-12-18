---
description: '詳細情報: 方法:マニフェストを C/C++ アプリケーションに埋め込む'
title: '方法: マニフェストを C/C++ アプリケーションに埋め込む'
ms.date: 05/06/2019
helpviewer_keywords:
- manifests [C++]
- embedding manifests
- makefiles, updating to embed manifest
ms.assetid: ec0bac69-2fdc-466c-ab0d-710a22974e5d
ms.openlocfilehash: ce3bdd56b994498b223857b80989247fe9919e4c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97156347"
---
# <a name="how-to-embed-a-manifest-inside-a-cc-application"></a>方法: マニフェストを C/C++ アプリケーションに埋め込む

ほとんどのシナリオで正しいランタイムの動作が保証されるため、アプリケーションまたはライブラリのマニフェストを最終的なバイナリの中に埋め込むことが推奨されてきました。 Visual Studio では、既定ではプロジェクトのビルド時にマニフェストの埋め込みを試みます。 詳細については、「[Visual Studio でのマニフェスト生成](manifest-generation-in-visual-studio.md)」を参照してください。 ただし、nmake を使用してアプリケーションをビルドする場合は、メイクファイルにいくつかの変更を加える必要があります。 このセクションでは、マニフェストを最終的なバイナリに自動的に埋め込むようにメイクファイルを変更する方法を示します。

## <a name="two-approaches"></a>2 つの方法

アプリケーションまたはライブラリにマニフェストを埋め込む方法は 2 つあります。

- インクリメンタル ビルドを実行していない場合は、次のようなコマンド ラインを使用して、ビルド後の手順としてマニフェストを直接埋め込むことができます。

   ```cmd
   mt.exe -manifest MyApp.exe.manifest -outputresource:MyApp.exe;1
   ```

   or

   ```cmd
   mt.exe -manifest MyLibrary.dll.manifest -outputresource:MyLibrary.dll;2
   ```

   EXE の場合は 1、DLL の場合は 2 を使用します。

- インクリメンタル ビルドを実行している場合は、次の手順を使用します。

  - バイナリをリンクして、MyApp.exe.manifest ファイルを生成します。

  - マニフェストをリソース ファイルに変換します。

  - 再リンク (インクリメンタル) を行って、マニフェスト リソースをバイナリに埋め込みます。

次の例では、両方の手法を組み込むようにメイクファイルを変更する方法を示します。

## <a name="makefiles-before"></a>メイクファイル (変更前)

1 つのファイルから構築された単純なアプリケーションである MyApp.exe の nmake スクリプトを検討します。

```
# build MyApp.exe
!if "$(DEBUG)" == "1"
CPPFLAGS=$(CPPFLAGS) /MDd
LFLAGS=$(LFLAGS) /INCREMENTAL
!else
CPPFLAGS=$(CPPFLAGS) /MD
!endif

MyApp.exe : MyApp.obj
    link $** /out:$@ $(LFLAGS)

MyApp.obj : MyApp.cpp

clean :
    del MyApp.obj MyApp.exe
```

このスクリプトを Visual Studio で変更せずに実行すると、MyApp が正常に作成されます。 さらに、実行時に依存アセンブリを読み込むためにオペレーティング システムによって使用される外部マニフェスト ファイル MyApp.exe.manifest も作成されます。

MyLibrary.dll の nmake スクリプトはよく似ています。

```
# build MyLibrary.dll
!if "$(DEBUG)" == "1"
CPPFLAGS=$(CPPFLAGS) /MDd
LFLAGS=$(LFLAGS) /DLL /INCREMENTAL

!else
CPPFLAGS=$(CPPFLAGS) /MD
LFLAGS=$(LFLAGS) /DLL

!endif

MyLibrary.dll : MyLibrary.obj
    link $** /out:$@ $(LFLAGS)

MyLibrary.obj : MyLibrary.cpp

clean :
    del MyLibrary.obj MyLibrary.dll
```

## <a name="makefiles-after"></a>メイクファイル (変更後)

埋め込まれたマニフェストを使用してビルドするには、元のメイクファイルに対して、4 つの小さな変更を加える必要があります。 MyApp.exe メイクファイルの場合:

```
# build MyApp.exe
!include makefile.inc
#^^^^^^^^^^^^^^^^^^^^ Change #1. (Add full path if necessary.)

!if "$(DEBUG)" == "1"
CPPFLAGS=$(CPPFLAGS) /MDd
LFLAGS=$(LFLAGS) /INCREMENTAL
!else
CPPFLAGS=$(CPPFLAGS) /MD
!endif

MyApp.exe : MyApp.obj
    link $** /out:$@ $(LFLAGS)
    $(_VC_MANIFEST_EMBED_EXE)
#^^^^^^^^^^^^^^^^^^^^^^^^^^^^ Change #2

MyApp.obj : MyApp.cpp

clean :
    del MyApp.obj MyApp.exe
    $(_VC_MANIFEST_CLEAN)
#^^^^^^^^^^^^^^^^^^^^^^^^ Change #3

!include makefile.targ.inc
#^^^^^^^^^^^^^^^^^^^^^^^^^ Change #4. (Add full path if necessary.)
```

MyLibrary.dll メイクファイルの場合:

```
# build MyLibrary.dll
!include makefile.inc
#^^^^^^^^^^^^^^^^^^^^ Change #1. (Add full path if necessary.)

!if "$(DEBUG)" == "1"
CPPFLAGS=$(CPPFLAGS) /MDd
LFLAGS=$(LFLAGS) /DLL /INCREMENTAL

!else
CPPFLAGS=$(CPPFLAGS) /MD
LFLAGS=$(LFLAGS) /DLL

!endif

MyLibrary.dll : MyLibrary.obj
    link $** /out:$@ $(LFLAGS)
    $(_VC_MANIFEST_EMBED_DLL)
#^^^^^^^^^^^^^^^^^^^^^^^^^^^^ Change #2.

MyLibrary.obj : MyLibrary.cpp

clean :
    del MyLibrary.obj MyLibrary.dll
    $(_VC_MANIFEST_CLEAN)
#^^^^^^^^^^^^^^^^^^^^^^^^ Change #3.

!include makefile.targ.inc
#^^^^^^^^^^^^^^^^^^^^^^^^^ Change #4. (Add full path if necessary.)
```

これで、実際の作業を行う 2 つのファイル (makefile.inc と makefile.targ.inc) がメイクファイルに含まれるようになりました。

makefile.inc を作成し、その中に以下をコピーします。

```
# makefile.inc -- Include this file into existing makefile at the very top.

# _VC_MANIFEST_INC specifies whether build is incremental (1 - incremental).
# _VC_MANIFEST_BASENAME specifies name of a temporary resource file.

!if "$(DEBUG)" == "1"
CPPFLAGS=$(CPPFLAGS) /MDd
LFLAGS=$(LFLAGS) /INCREMENTAL
_VC_MANIFEST_INC=1
_VC_MANIFEST_BASENAME=__VC90.Debug

!else
CPPFLAGS=$(CPPFLAGS) /MD
_VC_MANIFEST_INC=0
_VC_MANIFEST_BASENAME=__VC90

!endif

####################################################
# Specifying name of temporary resource file used only in incremental builds:

!if "$(_VC_MANIFEST_INC)" == "1"
_VC_MANIFEST_AUTO_RES=$(_VC_MANIFEST_BASENAME).auto.res
!else
_VC_MANIFEST_AUTO_RES=
!endif

####################################################
# _VC_MANIFEST_EMBED_EXE - command to embed manifest in EXE:

!if "$(_VC_MANIFEST_INC)" == "1"

#MT_SPECIAL_RETURN=1090650113
#MT_SPECIAL_SWITCH=-notify_resource_update
MT_SPECIAL_RETURN=0
MT_SPECIAL_SWITCH=
_VC_MANIFEST_EMBED_EXE= \
if exist $@.manifest mt.exe -manifest $@.manifest -out:$(_VC_MANIFEST_BASENAME).auto.manifest $(MT_SPECIAL_SWITCH) & \
if "%ERRORLEVEL%" == "$(MT_SPECIAL_RETURN)" \
rc /r $(_VC_MANIFEST_BASENAME).auto.rc & \
link $** /out:$@ $(LFLAGS)

!else

_VC_MANIFEST_EMBED_EXE= \
if exist $@.manifest mt.exe -manifest $@.manifest -outputresource:$@;1

!endif

####################################################
# _VC_MANIFEST_CLEAN - command to clean resources files generated temporarily:

!if "$(_VC_MANIFEST_INC)" == "1"

_VC_MANIFEST_CLEAN=-del $(_VC_MANIFEST_BASENAME).auto.res \
    $(_VC_MANIFEST_BASENAME).auto.rc \
    $(_VC_MANIFEST_BASENAME).auto.manifest

!else

_VC_MANIFEST_CLEAN=

!endif

# End of makefile.inc
####################################################
```

次に、**makefile.targ.inc** を作成し、その中に以下をコピーします。

```
# makefile.targ.inc - include this at the very bottom of the existing makefile

####################################################
# Commands to generate initial empty manifest file and the RC file
# that references it, and for generating the .res file:

$(_VC_MANIFEST_BASENAME).auto.res : $(_VC_MANIFEST_BASENAME).auto.rc

$(_VC_MANIFEST_BASENAME).auto.rc : $(_VC_MANIFEST_BASENAME).auto.manifest
    type <<$@
#include <winuser.h>
1RT_MANIFEST"$(_VC_MANIFEST_BASENAME).auto.manifest"
<< KEEP

$(_VC_MANIFEST_BASENAME).auto.manifest :
    type <<$@
<?xml version='1.0' encoding='UTF-8' standalone='yes'?>
<assembly xmlns='urn:schemas-microsoft-com:asm.v1' manifestVersion='1.0'>
</assembly>
<< KEEP

# end of makefile.targ.inc
```

## <a name="see-also"></a>関連項目

[C/C++ プログラムのマニフェスト生成についての理解](understanding-manifest-generation-for-c-cpp-programs.md)
