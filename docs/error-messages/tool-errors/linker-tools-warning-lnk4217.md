---
description: 詳細については、「リンカーツールの警告 LNK4217」を参照してください。
title: リンカー ツールの警告 LNK4217
ms.date: 07/23/2019
f1_keywords:
- LNK4217
helpviewer_keywords:
- LNK4217
ms.assetid: 280dc03e-5933-4e8d-bb8c-891fbe788738
ms.openlocfilehash: d3ace3586cf11da4dd87f00a58543c6d60fc1a10
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97150593"
---
# <a name="linker-tools-warning-lnk4217"></a>リンカー ツールの警告 LNK4217

> '*filename_1. .obj*' で定義されたシンボル '*symbol*' は、関数 '*function*' の '*filename_2 .obj*' によってインポートされています

シンボルが同じイメージ内のオブジェクトファイルで定義されているにもかかわらず、シンボルに[__declspec (dllimport)](../../cpp/dllexport-dllimport.md)が指定されました。 `__declspec(dllimport)`この警告を解決するには、修飾子を削除します。

## <a name="remarks"></a>解説

*symbol* は、イメージ内で定義されているシンボル名です。 *関数* は、シンボルをインポートする関数です。

この警告は、 [/clr](../../build/reference/clr-common-language-runtime-compilation.md) オプションを使用してコンパイルした場合には表示されません。

LNK4217 は、2つのモジュールをリンクしようとした場合にも発生する可能性があります。代わりに、最初のモジュールのインポートライブラリを使用して2番目のモジュールをコンパイルする必要があります。

```cpp
// main.cpp
__declspec(dllimport) void func();

int main()
{
    func();
    return 0;
}

```

この場合、次のようになります。

```cpp
// tt.cpp
// compile with: /c
void func() {}
```

次に示すように、これら2つのモジュールをコンパイルしようとすると、LNK4217 が発生します。

```cmd
cl.exe /c main.cpp tt.cpp
link.exe main.obj tt.obj
```

このエラーを解決するには、2つのファイルをコンパイルした後、次のように .tt を lib.exe に渡して .lib ファイルを作成し、次に示すように、.tt を含む .obj をリンクします。

```cmd
cl.exe /c main.cpp tt.cpp
lib.exe tt.obj /export:func /def
link.exe main.obj tt.lib
```

## <a name="see-also"></a>関連項目

[リンカーツールの警告 LNK4049](linker-tools-warning-lnk4049.md) \
[リンカーツールの警告 LNK4286](linker-tools-warning-lnk4286.md) \
[dllexport、dllimport](../../cpp/dllexport-dllimport.md)
