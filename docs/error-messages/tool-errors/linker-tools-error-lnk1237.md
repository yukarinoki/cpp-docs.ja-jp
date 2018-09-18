---
title: リンカ ツール エラー LNK1237 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1237
dev_langs:
- C++
helpviewer_keywords:
- LNK1237
ms.assetid: 8722ffa8-096a-4bb0-85f9-f3aa0e10872a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f9ada38fcf3a706f7852f49f60f677fb5dc10d7e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46065297"
---
# <a name="linker-tools-error-lnk1237"></a>リンカ ツール エラー LNK1237

コードの生成中には、コンパイラはシンボル 'symbol' は 'module'/GL でコンパイルされたモジュールで定義されているへの参照を導入しました。

コードの生成中に、コンパイラ定義のコンパイルを後で解決されるシンボル **/GL**します。 `symbol` 既に導入されており、後でコンパイルされた定義に解決される記号 **/GL**します。

詳細については、「[/GL (プログラム全体の最適化)](../../build/reference/gl-whole-program-optimization.md)」を参照してください。

LNK1237 を解決するには、コンパイルされないシンボルは、 **/GL**使用または[/INCLUDE (シンボル参照の強制)](../../build/reference/include-force-symbol-references.md)シンボルへの参照を強制します。

## <a name="example"></a>例

次の例では、LNK1237 が生成されます。 このエラーを解決するのには LNK1237_a.cpp で配列を初期化されず、追加 **/include: _chkstk**リンク コマンド。

```
// LNK1237_a.cpp
int main() {
   char c[5000] = {0};
}
```

```
// LNK1237_b.cpp
// compile with: /GS- /GL /c LNK1237_a.cpp
// processor: x86
// post-build command: (lib LNK1237_b.obj /LTCG & link LNK1237_a.obj LNK1237_b.lib /nodefaultlib /entry:main /LTCG)
extern "C" void _chkstk(size_t s) {}
```