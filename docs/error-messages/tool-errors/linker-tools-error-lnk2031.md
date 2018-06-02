---
title: リンカ ツール エラー LNK2031 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2031
dev_langs:
- C++
helpviewer_keywords:
- LNK2031
ms.assetid: 18ed4b6e-3e75-443c-bbd8-2f6030dc89ee
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d86ea6da8a73d9ba2427e9455c4fca87cd32dd2b
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/01/2018
ms.locfileid: "34703666"
---
# <a name="linker-tools-error-lnk2031"></a>リンカ ツール エラー LNK2031

> p/invoke を生成できません"*function_declaration*" *decorated_name*; 呼び出し規約がメタデータに見つかりません。

## <a name="remarks"></a>コメント

ネイティブ関数を純粋なイメージにインポートするは、ネイティブと純粋なコンパイルの間で暗黙の呼び出し規約が異なることに注意してください。 純粋なイメージの詳細については、次を参照してください。[純粋なコードと検証可能なコード (C + + CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md)です。

**/Clr: 純粋な**コンパイラ オプションは Visual Studio 2015 では廃止され、Visual Studio 2017 でサポートされていません。

## <a name="example"></a>例

このコード サンプルは、ネイティブ、エクスポートされた関数の呼び出し規約は暗黙的に持つコンポーネントを生成[_ _cdecl](../../cpp/cdecl.md)です。

```cpp
// LNK2031.cpp
// compile with: /LD
extern "C" {
   __declspec(dllexport) int func() { return 3; }
};
```

## <a name="example"></a>例

次の例では、純粋なネイティブ関数を使用するクライアントを作成します。 ただし、下にある呼び出し規約 **/clr: 純粋な**は[_ _clrcall](../../cpp/clrcall.md)です。 次の例では、LNK2031 が生成されます。

```cpp
// LNK2031_b.cpp
// compile with: /clr:pure LNK2031.lib
// LNK2031 expected
extern "C" int func();

int main() {
   return func();
}
```

## <a name="example"></a>例

次の例では、純粋なイメージからネイティブ関数を使用する方法を示します。 明示的に注意してください **_ _cdecl**呼び出し規約の指定子。

```cpp
// LNK2031_c.cpp
// compile with: /clr:pure LNK2031.lib
extern "C" int __cdecl func();

int main() {
   return func();
}
```