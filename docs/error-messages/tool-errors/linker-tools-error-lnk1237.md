---
description: 詳細については、「リンカツール Error LNK1237」を参照してください。
title: リンカ ツール エラー LNK1237
ms.date: 11/04/2016
f1_keywords:
- LNK1237
helpviewer_keywords:
- LNK1237
ms.assetid: 8722ffa8-096a-4bb0-85f9-f3aa0e10872a
ms.openlocfilehash: ba6a0d23eea4d8d555115950fcd54a5e4f6a8bde
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193983"
---
# <a name="linker-tools-error-lnk1237"></a>リンカ ツール エラー LNK1237

コード生成中に、コンパイラによって、/GL を使用してコンパイルされたモジュール ' module ' で定義されたシンボル ' symbol ' への参照が導入されました

コードの生成中、コンパイラは、後でコンパイル済みの定義に解決されるシンボルを導入しない **でください。** `symbol` は、 **/gl** を使用してコンパイルされた定義に対して後で解決されたシンボルです。

詳細については、「[/GL (プログラム全体の最適化)](../../build/reference/gl-whole-program-optimization.md)」を参照してください。

LNK1237 を解決するには、 **/gl** を使用してシンボルをコンパイルしないようにするか、または [/INCLUDE (シンボル参照を強制する)](../../build/reference/include-force-symbol-references.md) を使用してシンボルへの参照を強制的に実行します。

## <a name="example"></a>例

次の例では、LNK1237 が生成されます。 このエラーを解決するには、LNK1237_a の配列を初期化して、 **/include: __chkstk** を link コマンドに追加しないでください。

```cpp
// LNK1237_a.cpp
int main() {
   char c[5000] = {0};
}
```

```cpp
// LNK1237_b.cpp
// compile with: /GS- /GL /c LNK1237_a.cpp
// processor: x86
// post-build command: (lib LNK1237_b.obj /LTCG & link LNK1237_a.obj LNK1237_b.lib /nodefaultlib /entry:main /LTCG)
extern "C" void _chkstk(size_t s) {}
```
