---
description: '詳細情報: C ビット処理演算子'
title: C ビット処理演算子
ms.date: 01/29/2018
helpviewer_keywords:
- '| operator, bitwise operators'
- bitwise operators, Visual C
- bitwise operators
- operators [C], bitwise
- ^ operator, bitwise operators
- AND operator
- ampersand operator (&)
- ^ operator
- '& operator, bitwise operators'
ms.assetid: e22127b1-9a2d-4876-b01d-c8f72cec3317
ms.openlocfilehash: 8cbdb5309d5351f77306007e8acd1675be5e2a35
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97211584"
---
# <a name="c-bitwise-operators"></a>C ビット処理演算子

ビット処理演算子は、ビットごとの AND ( **&** )、ビットごとの排他的 OR ( **^** )、およびビットごとの包括的 OR ( **&#124;** ) 演算を行います。

## <a name="syntax"></a>構文

*AND-expression*: &nbsp;&nbsp;*equality-expression* &nbsp;&nbsp;*AND-expression* **&** *equality-expression*

*exclusive-OR-expression*:&nbsp;&nbsp;*AND-expression* &nbsp;&nbsp;*exclusive-OR-expression* **^** *AND-expression*

*inclusive-OR-expression*: &nbsp;&nbsp;*exclusive-OR-expression* &nbsp;&nbsp;*inclusive-OR-expression* &#124; *exclusive-OR-expression*

ビット処理演算子のオペランドは、整数型である必要がありますが、それぞれの型が異なっていてもかまいません。 これらの演算子は、通常の算術変換を実行します。結果の型は変換後のオペランドの型です。

C のビット処理演算子について、以下に説明します。

|演算子|説明|
|--------------|-----------------|
|**&**|ビットごとの AND 演算子は、最初のオペランドの各ビットを 2 番目のオペランドの対応するビットと比較します。 両方のビットが 1 の場合、対応する結果のビットは 1 に設定されます。 それ以外の場合は、対応する結果ビットが 0 に設定されます。|
|**^**|ビットごとの排他的 OR 演算子は、最初のオペランドの各ビットを 2 番目のオペランドの対応するビットと比較します。 一方のビットが 0 でもう一方のビットが 1 の場合、対応する結果のビットは 1 に設定されます。 それ以外の場合は、対応する結果ビットが 0 に設定されます。|
|**&#124;**|ビットごとの包括的 OR 演算子は、最初のオペランドの各ビットを 2 番目のオペランドの対応するビットと比較します。 どちらかのビットが 1 の場合、対応する結果のビットは 1 に設定されます。 それ以外の場合は、対応する結果ビットが 0 に設定されます。|

## <a name="examples"></a>使用例

これらの宣言が、次の 3 つの例で使用されています。

```C
short i = 0xAB00;
short j = 0xABCD;
short n;

n = i & j;
```

この最初の例で `n` に割り当てられる結果は、`i` (16 進数の 0xAB00) と同じです。

```C
n = i | j;

n = i ^ j;
```

2 番目の例のビットごとの包括的 OR の結果は値 0xABCD (16 進数) になり、3 番目の例のビットごとの排他的 OR は 0xCD (16 進数) を生成します。

**Microsoft 固有の仕様**

符号付き整数に対するビットごとの演算の結果は、ANSI C 規格に従って、実装定義になります。 Microsoft C コンパイラでは、符号付き整数のビットごとの演算は、符号なし整数のビットごとの演算と同じように動作します。 たとえば、`-16 & 99` は、バイナリでは次のように表されます。

```Expression
  11111111 11110000
& 00000000 01100011
  _________________
  00000000 01100000
```

ビットごとの AND の結果は 10 進数の 96 です。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[ビット処理 AND 演算子: &](../cpp/bitwise-and-operator-amp.md)<br/>
[ビット処理排他的 OR 演算子: ^](../cpp/bitwise-exclusive-or-operator-hat.md)<br/>
[ビット処理包括的 OR 演算子: &#124;](../cpp/bitwise-inclusive-or-operator-pipe.md)
