---
description: 詳細については、「Delay-Loaded DLL の明示的なアンロード」を参照してください。
title: 遅延読み込みした DLL の明示的なアンロード
ms.date: 11/04/2016
helpviewer_keywords:
- /DELAY:UNLOAD linker option
- DELAY:UNLOAD linker option
- __FUnloadDelayLoadedDLL2
- delayed loading of DLLs, unloading
ms.assetid: 1c4c5172-fd06-45d3-9e4f-f12343176b3c
ms.openlocfilehash: 03df08487acc1be05226021d6b7c1593eb0f031b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192383"
---
# <a name="explicitly-unloading-a-delay-loaded-dll"></a>遅延読み込みした DLL の明示的なアンロード

[/Delay](delay-delay-load-import-settings.md): unload リンカーオプションを使用すると、遅延読み込みされた DLL をアンロードできます。 既定では、コードが DLL をアンロードするとき (/delay: unload および **__FUnloadDelayLoadedDLL2** を使用)、遅延読み込みされたインポートは、インポートアドレステーブル (IAT) に残ります。 ただし、リンカーコマンドラインで/delay: unload を使用する場合、ヘルパー関数は DLL の明示的なアンロードをサポートし、IAT を元の形式にリセットします。現在、無効なポインターは上書きされます。 IAT は、 [ImgDelayDescr](calling-conventions-parameters-and-return-type.md) 内のフィールドであり、元の iat のコピー (存在する場合) のアドレスが含まれています。

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

### <a name="comments"></a>説明

遅延読み込みされた DLL のアンロードに関する重要な注意事項:

- **__FUnloadDelayLoadedDLL2** 関数の実装については、\VC7\INCLUDE\DELAYHLP. ファイルを参照してください。.CPP.

- **__FUnloadDelayLoadedDLL2** 関数の name パラメーターは、インポートライブラリに含まれているもの (大文字と小文字を含む) を正確に一致させる必要があります (この文字列はイメージのインポートテーブルにも含まれます)。 インポートライブラリの内容は、 [DUMPBIN/依存](dependents.md)関係を使用して表示できます。 大文字と小文字を区別せずに文字列を一致させる必要がある場合は、 **__FUnloadDelayLoadedDLL2** を更新して、CRT 文字列関数または Windows API 呼び出しのいずれかを使用できます。

詳細について [は、「Delay-Loaded DLL のアンロード](unloading-a-delay-loaded-dll.md) 」を参照してください。

## <a name="see-also"></a>関連項目

[リンカーによる Delay-Loaded Dll のサポート](linker-support-for-delay-loaded-dlls.md)
