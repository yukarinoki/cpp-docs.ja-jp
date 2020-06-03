---
title: リンカ ツール エラー LNK1179
ms.date: 11/04/2016
f1_keywords:
- LNK1179
helpviewer_keywords:
- LNK1179
ms.assetid: 4b1536d7-0d3d-4f29-a9c1-6fa5cf6cb665
ms.openlocfilehash: d85693cec11ef53a6bbbb60d8ced716d2a0bb131
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754337"
---
# <a name="linker-tools-error-lnk1179"></a>リンカ ツール エラー LNK1179

無効または壊れたファイル: 重複する COMDAT 'ファイル名'

オブジェクト モジュールには、同じ名前の COMDA が 2 つ以上含まれています。

このエラーは、外部名の長さを制限する /H、COMDAT の関数をパッケージ化する[/Gy](../../build/reference/gy-enable-function-level-linking.md)を使用して発生する可能性があります。 [/H](../../build/reference/h-restrict-length-of-external-names.md)

## <a name="example"></a>例

次のコードでは、`function1``function2`最初の 8 文字で同じです。 **/Gy**と **/H8**を指定してコンパイルすると、リンク エラーが発生します。

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
