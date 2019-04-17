---
title: リンカー ツールの警告 LNK4217
ms.date: 04/15/2019
f1_keywords:
- LNK4217
helpviewer_keywords:
- LNK4217
ms.assetid: 280dc03e-5933-4e8d-bb8c-891fbe788738
ms.openlocfilehash: f1ea3cd0a8770571ae5c55d29a901c134311550f
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/17/2019
ms.locfileid: "59674241"
---
# <a name="linker-tools-warning-lnk4217"></a>リンカー ツールの警告 LNK4217

> シンボル '*シンボル*'で定義されている'*filename_1.obj*'によってインポートされる'*filename_2.obj*'function' で*関数*'

[_declspec](../../cpp/dllexport-dllimport.md)記号が同じイメージのオブジェクト ファイルで定義されている場合でも、シンボルが指定されました。 削除、`__declspec(dllimport)`修飾子をこの警告を解決します。

## <a name="remarks"></a>Remarks

*シンボル*は、イメージ内で定義されているシンボルの名前です。 *関数*関数では、シンボルをインポートしています。

使用してコンパイルするときに、この警告は表示されない、 [/clr](../../build/reference/clr-common-language-runtime-compilation.md)オプション。

LNK4217 は、最初のモジュールのインポート ライブラリと 2 番目のモジュールをコンパイルする代わりと同時に、2 つのモジュールをリンクしようとした場合にも発生します。

```cpp
// LNK4217.cpp
// compile with: /LD
#include "windows.h"
__declspec(dllexport) void func(unsigned short*) {}
```

この場合、次のようになります。

```cpp
// LNK4217b.cpp
// compile with: /c
#include "windows.h"
__declspec(dllexport) void func(unsigned short*) {}
```

これら 2 つのモジュールをリンクしようとすると LNK4217 が発生します。 解決するのには、最初のサンプルのインポート ライブラリと 2 番目のサンプルをコンパイルします。

## <a name="see-also"></a>関連項目

[リンカー ツールの警告 LNK4049](linker-tools-warning-lnk4049.md) \
[リンカー ツールの警告 LNK4286](linker-tools-warning-lnk4286.md) \
[dllexport、dllimport](../../cpp/dllexport-dllimport.md)