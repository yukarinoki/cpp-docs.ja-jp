---
description: 詳細については、「遅延読み込みされた DLL の明示的なアンロード」を参照してください。
title: 遅延読み込みされた DLL の明示的なアンロード
ms.date: 01/19/2021
helpviewer_keywords:
- /DELAY:UNLOAD linker option
- DELAY:UNLOAD linker option
- __FUnloadDelayLoadedDLL2
- delayed loading of DLLs, unloading
ms.openlocfilehash: b4e137f293c6497e234a7bb93bd16b5bb6887741
ms.sourcegitcommit: 3d9cfde85df33002e3b3d7f3509ff6a8dc4c0a21
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "98666889"
---
# <a name="explicitly-unload-a-delay-loaded-dll"></a>遅延読み込みされた DLL の明示的なアンロード

[`/delay:unload`](delay-delay-load-import-settings.md)リンカーオプションを使用すると、遅延読み込みされた DLL をコードで明示的にアンロードできます。 既定では、コードが DLL をアンロードするときに、遅延読み込みされたインポートは、インポートアドレステーブル (IAT) に残ります。 ただし、リンカーコマンドラインでを使用する場合、 **`/delay:unload`** ヘルパー関数は、呼び出しによる DLL の明示的なアンロードをサポート `__FUnloadDelayLoadedDLL2` し、IAT を元の形式にリセットします。 現在、無効なポインターが上書きされます。 IAT は、 [`ImgDelayDescr`](calling-conventions-parameters-and-return-type.md) 元の iat のコピー (存在する場合) のアドレスを含む構造体のフィールドです。

## <a name="example"></a>例

### <a name="code"></a>コード

```C
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

遅延読み込みされた DLL のアンロードに関する重要な注意事項:

- 関数の実装は、ファイルの `__FUnloadDelayLoadedDLL2` *`delayhlp.cpp`* VC ディレクトリで確認でき *`include`* ます。

- *`name`* 関数のパラメーターは、 `__FUnloadDelayLoadedDLL2` インポートライブラリに含まれるものと完全に一致する必要があります (ケースを含む)。 (その文字列は、イメージのインポートテーブルにもあります)。インポートライブラリの内容は、を使用して表示でき [`DUMPBIN /DEPENDENTS`](dependents.md) ます。 大文字と小文字を区別せずに文字列を一致させる場合は、を更新して、大文字と小文字を区別しない `__FUnloadDelayLoadedDLL2` CRT 文字列関数または WINDOWS API 呼び出しのいずれかを使用できます。

詳細については、「 [遅延読み込みされた DLL のアンロード](unloading-a-delay-loaded-dll.md)」を参照してください。

## <a name="see-also"></a>こちらもご覧ください

[リンカーによる DLL の遅延読み込み](linker-support-for-delay-loaded-dlls.md)
