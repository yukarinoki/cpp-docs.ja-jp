---
title: リンカ ツール エラー LNK2031
ms.date: 11/04/2016
f1_keywords:
- LNK2031
helpviewer_keywords:
- LNK2031
ms.assetid: 18ed4b6e-3e75-443c-bbd8-2f6030dc89ee
ms.openlocfilehash: 096ccb7ff443d24e0d53e73a5950faa1e85aeae6
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80194565"
---
# <a name="linker-tools-error-lnk2031"></a>リンカ ツール エラー LNK2031

> "*function_declaration*" *decorated_name*; に対して p/invoke を生成できません。メタデータに呼び出し規約がありません

## <a name="remarks"></a>解説

ネイティブ関数を純粋なイメージにインポートしようとすると、暗黙的な呼び出し規約がネイティブコンパイルと純粋コンパイルで異なることに注意してください。 純粋なイメージの詳細については、「[純粋でC++検証可能なコード (/cli)](../../dotnet/pure-and-verifiable-code-cpp-cli.md)」を参照してください。

**/Clr: pure**コンパイラオプションは visual studio 2015 で非推奨とされており、visual studio 2017 ではサポートされていません。

## <a name="example"></a>例

このコードサンプルでは、エクスポートされたネイティブ関数を持つコンポーネントを生成します。この関数の呼び出し規約は、暗黙的に[__cdecl](../../cpp/cdecl.md)ます。

```cpp
// LNK2031.cpp
// compile with: /LD
extern "C" {
   __declspec(dllexport) int func() { return 3; }
};
```

## <a name="example"></a>例

次の例では、ネイティブ関数を使用する純粋なクライアントを作成します。 ただし、 **/clr: pure**の呼び出し規約は[__clrcall](../../cpp/clrcall.md)。 次の例では、LNK2031 が生成されます。

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

次のサンプルは、純粋なイメージからネイティブ関数を使用する方法を示しています。 明示的な **__cdecl**呼び出し規約指定子に注意してください。

```cpp
// LNK2031_c.cpp
// compile with: /clr:pure LNK2031.lib
extern "C" int __cdecl func();

int main() {
   return func();
}
```
