---
description: '詳細情報: C 論理演算子'
title: C 論理演算子
ms.date: 06/14/2018
helpviewer_keywords:
- logical operators, expression sequence points
- logical operators, C
- logical AND operator
- '|| operator'
- operators [C], logical
- short-circuit evaluation
- '&& operator'
- logical OR operator
ms.assetid: c0a4e766-ad56-4300-bf76-b28dc0e19b43
ms.openlocfilehash: 58527e4702abce6d05f7f8e6d5aed2d7c17eca94
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97300308"
---
# <a name="c-logical-operators"></a>C 論理演算子

論理演算子は、論理 AND ( **&&** ) 演算と論理 OR ( **||** ) 演算を実行します。

## <a name="syntax"></a>構文

*logical-AND-expression*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*inclusive-OR-expression*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*logical-AND-expression*  **&&**  *inclusive-OR-expression*

*logical-OR-expression*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*logical-AND-expression*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*logical-OR-expression*  **&#124;&#124;**  *logical-AND-expression*

## <a name="remarks"></a>Remarks

論理演算子は通常の算術変換を実行しません。 代わりに、0 との等価性において各オペランドを評価します。 論理演算の結果は 0 または 1 になります。 結果の型は **`int`** です。

C の論理演算子について、以下に説明します。

|演算子|説明|
|--------------|-----------------|
|**&&**|両方のオペランドが 0 以外の値の場合、論理 AND 演算子は値 1 を生成します。 どちらかのオペランドが 0 の場合、結果も 0 となります。 論理 AND 演算の 1 つ目のオペランドが 0 となる場合、2 つ目のオペランドは評価されません。|
|**&#124;&#124;**|論理 OR 演算子は、そのオペランドに対して包括 OR 演算を実行します。 両方のオペランドの値が 0 の場合、結果は 0 です。 どちらかのオペランドの値が 0 以外の場合、結果は 1 になります。 論理 OR 演算の 1 つ目のオペランドにゼロ以外の値が含まれる場合、2 つ目のオペランドは評価されません。|

論理 AND 式と論理 OR 式のオペランドは左から右に評価されます。 1 つ目のオペランドの値で演算の結果を確認できる場合、2 つ目のオペランドは評価されません。 これは、"ショートサーキット評価" と呼ばれます。 1 つ目のオペランドの後にシーケンス ポイントがあります。 詳細については、「[シーケンス ポイント](../c-language/c-sequence-points.md)」を参照してください。

## <a name="examples"></a>使用例

論理演算子の例を次に示します。

```C
int w, x, y, z;

if ( x < y && y < z )
    printf( "x is less than z\n" );
```

この例では、`x` が `y` 未満で、`y` が `z` 未満である場合に、**printf** 関数が呼び出され、メッセージが出力されます。 `x` が `y` より大きい場合、2 つ目のオペランド (`y < z`) は評価されず、何も出力されません。 このことは、2 つ目のオペランドが他の理由で依存される副作用をもたらす場合、問題となる可能性があることに注意してください。

```C
printf( "%d" , (x == w || x == y || x == z) );
```

この例では、`x` が `w`、`y`、または `z` と等しい場合、**printf** 関数の 2 番目の引数が true に評価され、値 1 が出力されます。 それ以外の場合は、false と評価され、値 0 が出力されます。 条件の 1 つが true と評価されると、直ちに評価が終了します。

## <a name="see-also"></a>関連項目

- [論理 AND 演算子: &&](../cpp/logical-and-operator-amp-amp.md)
- [論理 OR 演算子: &#124;&#124;](../cpp/logical-or-operator-pipe-pipe.md)
