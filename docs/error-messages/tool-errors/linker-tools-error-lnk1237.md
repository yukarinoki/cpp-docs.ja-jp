---
title: リンカ ツール エラー LNK1237
ms.date: 11/04/2016
f1_keywords:
- LNK1237
helpviewer_keywords:
- LNK1237
ms.assetid: 8722ffa8-096a-4bb0-85f9-f3aa0e10872a
ms.openlocfilehash: ae1a397cdcc10cd89fd046a94e78c15dd46dceed
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50581325"
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