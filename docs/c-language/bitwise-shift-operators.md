---
title: ビット処理シフト演算子 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- operators [C++], bitwise
- shift operators, bitwise
- bitwise-shift operators
- operators [C++], shift
ms.assetid: d0485785-5c72-47e1-a7c0-0adde03ade23
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4dfb5ffe13d8813eff0e3db4978eb1799bee1a85
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46020122"
---
# <a name="bitwise-shift-operators"></a>ビット処理シフト演算子

シフト演算子では、2 番目のオペランドで指定された位置の数だけ最初のオペランドが左 (`<<`) または右 (`>>`) にシフトされます。

## <a name="syntax"></a>構文

*shift-expression*: *additive-expression*

*shift-expression*  `<<`  *additive-expression shift-expression*  `>>`  *additive-expression*

どちらのオペランドも整数値である必要があります。 これらの演算子は通常の算術変換を実行します。結果の型は、変換後の左オペランドの型です。

左方向へシフトする場合、空いた右のビットは 0 に設定されます。 右方向へシフトする場合、空いた左ビットは、変換後に最初のオペランドの型に基づいて埋められます。 型が `unsigned` の場合は 0 に設定されます。 それ以外の場合は、符号ビットのコピーで埋められます。 オーバーフローのない左シフト演算子の例を次に示します。

```
expr1 << expr2
```

上記のステートメントは 2<sup>expr2</sup> での乗算と同じになります。 右シフト演算子の例を次に示します。

```
expr1 >> expr2
```

上記のステートメントは、`expr1` が符号なし、または負の値ではない場合、2<sup>expr2</sup> での除算と同じになります。

シフト演算の結果は、2 番目のオペランドが負である場合、または右オペランドが、昇格した左オペランドのビット単位の幅以上の場合、未定義です。

シフト演算子によって実行される変換ではオーバーフロー条件やアンダーフロー条件が提供されないため、シフト演算の結果を変換後の最初のオペランドの型で表すことができない場合、情報が失われる可能性があります。

```
unsigned int x, y, z;

x = 0x00AA;
y = 0x5500;

z = ( x << 8 ) + ( y >> 8 );
```

この例では、`x` は左に 8 シフトし、`y` は右に 8 シフトしています。 0xAA55 の場合、シフトされた値が追加され、`z` に代入されます。

負の値を右へシフトすると、元の値の 1/2 (切り捨て) になります。 たとえば、-253 (バイナリ 11111111 00000011) を 1 ビット右にシフトすると、-127 (バイナリ 11111111 10000001) になります。 正の 253 を右にシフトすると +126 になります。

右シフトでは符号ビットが保持されます。 符号付き整数を右にシフトすると、最上位ビットはセットされたままになります。 符号なし整数を右にシフトすると、最上位ビットはクリアされます。

## <a name="see-also"></a>参照

[左シフト演算子および右シフト演算子 (<< および >>)](../cpp/left-shift-and-right-shift-operators-input-and-output.md)