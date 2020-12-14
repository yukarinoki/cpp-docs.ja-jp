---
description: 詳細については、「リンカツール Error LNK1179」を参照してください。
title: リンカ ツール エラー LNK1179
ms.date: 11/04/2016
f1_keywords:
- LNK1179
helpviewer_keywords:
- LNK1179
ms.assetid: 4b1536d7-0d3d-4f29-a9c1-6fa5cf6cb665
ms.openlocfilehash: 691476eeffadece2436518c5249ca523adca51c2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97253443"
---
# <a name="linker-tools-error-lnk1179"></a>リンカ ツール エラー LNK1179

ファイルが無効であるか壊れています: COMDAT ' filename ' が重複しています

オブジェクトモジュールに、同じ名前の複数の Comdat が含まれています。

このエラーは、外部名の長さを制限する [/h](../../build/reference/h-restrict-length-of-external-names.md)を使用することによって発生することがあります。また、/gy に関数をパッケージ化する [/gy](../../build/reference/gy-enable-function-level-linking.md)を使用することもできます。

## <a name="example"></a>例

次のコードで `function1` は、と `function2` は最初の8文字と同じです。 **/Gy** と **/H8** を使用してコンパイルすると、リンクエラーが発生します。

```cpp
void function1(void);
void function2(void);

int main() {
    function1();
    function2();
}

void function1(void) {}
void function2(void) {}
```
