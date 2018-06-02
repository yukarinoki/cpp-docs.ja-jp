---
title: リンカ ツール エラー LNK2028 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2028
dev_langs:
- C++
helpviewer_keywords:
- LNK2028
ms.assetid: e2b03293-6066-464d-a050-ce747bcf7f0e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e9c8eaa03927f51acd3c3d84731e9ef2b282b7c6
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/01/2018
ms.locfileid: "34704155"
---
# <a name="linker-tools-error-lnk2028"></a>リンカ ツール エラー LNK2028

"*exported_function*"(*decorated_name*) 関数で参照される"*function_containing_function_call*"(*decorated_name*)

## <a name="remarks"></a>コメント

ネイティブ関数を純粋なイメージにインポートするは、ネイティブと純粋なコンパイルの間で暗黙の呼び出し規約が異なることに注意してください。

**/Clr: 純粋な**コンパイラ オプションは Visual Studio 2015 では廃止され、Visual Studio 2017 でサポートされていません。

## <a name="example"></a>例

このコード サンプルは、ネイティブ、エクスポートされた関数の呼び出し規約は暗黙的に持つコンポーネントを生成[_ _cdecl](../../cpp/cdecl.md)です。

```cpp
// LNK2028.cpp
// compile with: /LD
__declspec(dllexport) int func() {
   return 3;
}
```

## <a name="example"></a>例

次の例では、純粋なネイティブ関数を使用するクライアントを作成します。 ただし、下にある呼び出し規約 **/clr: 純粋な**は[_ _clrcall](../../cpp/clrcall.md)です。 次の例では、LNK2028 が生成されます。

```cpp
// LNK2028_b.cpp
// compile with: /clr:pure lnk2028.lib
// LNK2028 expected
int func();

int main() {
   return func();
}
```