---
title: 遅延読み込みした DLL の明示的なアンロード |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- /DELAY:UNLOAD linker option
- DELAY:UNLOAD linker option
- __FUnloadDelayLoadedDLL2
- delayed loading of DLLs, unloading
ms.assetid: 1c4c5172-fd06-45d3-9e4f-f12343176b3c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 171acf9689c01649b86c2383d17136c926e25c57
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32374175"
---
# <a name="explicitly-unloading-a-delay-loaded-dll"></a>遅延読み込みした DLL の明示的なアンロード
[/Delay](../../build/reference/delay-delay-load-import-settings.md): アンロード リンカー オプションでは、遅延読み込みされた DLL をアンロードすることができます。 既定で、コードが DLL をアンロードするとき (/delay:unload を使用して **__FUnloadDelayLoadedDLL2**)、インポート アドレス テーブル (IAT) に、遅延読み込みしたインポートが残ります。 ただし、/delay:unload リンカー コマンドラインを使用する場合、ヘルパー関数がサポート、IAT をリセットする元の形式に、DLL の明示的なアンロード無効になったポインターが上書きされます。 IAT が内のフィールド、 [ImgDelayDescr](../../build/reference/calling-conventions-parameters-and-return-type.md) (ある場合) 元の IAT のコピーのアドレスを格納します。  
  
## <a name="example"></a>例  
  
### <a name="code"></a>コード  
  
```  
// link with /link /DELAYLOAD:MyDLL.dll /DELAY:UNLOAD  
#include <windows.h>  
#include <delayimp.h>  
#include "MyDll.h"  
#include <stdio.h>  
  
#pragma comment(lib, "delayimp")  
#pragma comment(lib, "MyDll")  
int main()  
{  
    BOOL TestReturn;  
    // MyDLL.DLL will load at this point  
    fnMyDll();  
  
    //MyDLL.dll will unload at this point  
    TestReturn = __FUnloadDelayLoadedDLL2("MyDll.dll");  
  
    if (TestReturn)  
        printf_s("\nDLL was unloaded");  
    else  
        printf_s("\nDLL was not unloaded");  
}  
```  
  
### <a name="comments"></a>コメント  
 遅延読み込みした DLL のアンロードに重要なメモ:  
  
-   実装を見つけることができます、 **__FUnloadDelayLoadedDLL2**ファイル内の関数 \VC7\INCLUDE\DELAYHLP です。CPP です。  
  
-   Name パラメーター、 **__FUnloadDelayLoadedDLL2**関数が正確に一致 (大文字) を含むどのようなインポート ライブラリが含まれています (つまり文字列は、イメージのインポート テーブルにも)。 インポート ライブラリの内容を表示する[DUMPBIN/DEPENDENTS](../../build/reference/dependents.md)です。 大文字と小文字の文字列の一致が必要な場合は、更新 **__FUnloadDelayLoadedDLL2** CRT 文字列関数、または Windows API の呼び出しの 1 つを使用します。  
  
 参照してください[アンロード、「](../../build/reference/unloading-a-delay-loaded-dll.md)詳細についてはします。  
  
## <a name="see-also"></a>関連項目  
 [リンカーによる DLL の遅延読み込み](../../build/reference/linker-support-for-delay-loaded-dlls.md)