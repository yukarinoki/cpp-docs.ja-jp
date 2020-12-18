---
description: '詳細情報: `switch` ステートメント (C)'
title: switch ステートメント (C)
ms.date: 04/25/2020
f1_keywords:
- switch
helpviewer_keywords:
- switch keyword [C]
ms.assetid: fbede014-23bd-4ab1-8094-c8d9d9cb963a
no-loc:
- switch
- case
- default
- break
ms.openlocfilehash: f6089505ac47c657e151a60d6061a79ee0fd3cb8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97114443"
---
# <a name="no-locswitch-statement-c"></a>`switch` ステートメント (C)

**`switch`** および **`case`** ステートメントを使用すると、複雑な条件付き処理や分岐処理を制御しやすくなります。 **`switch`** ステートメントは、本体内のステートメントに制御を移します。

## <a name="syntax"></a>構文

> *`selection-statement`*:\
> &nbsp;&nbsp;&nbsp;&nbsp; **`switch (`**&nbsp;*`expression`* &nbsp;**`)`**&nbsp;*`statement`*

> *`labeled-statement`*:\
> &nbsp;&nbsp;&nbsp;&nbsp; **`case`**&nbsp;*`constant-expression`*&nbsp;**`:`**&nbsp;*`statement`*\
> &nbsp;&nbsp;&nbsp;&nbsp; **`default`**&nbsp;**`:`**&nbsp;*`statement`*

## <a name="remarks"></a>Remarks

**`switch`** ステートメントを指定すると、 *`expression`* の値に応じて、ステートメント本体の 1 つの *`labeled-statement`* にコントロールが転送されます。

*`expression`* の値 および各 *`constant-expression`* には整数型を指定する必要があります。 *`constant-expression`* は、コンパイル時に明確な定数の整数値を持つ必要があります。

コントロールは、 *`constant-expression`* 値が *`expression`* の値と一致する **`case`** ステートメントに渡されます。 **`switch`** ステートメントには、任意の数の **`case`** インスタンスを含めることができます。 ただし、同じ **`switch`** ステートメント内で 2 つの *`constant-expression`* 値が同じ値を持つことはできません。 **`switch`** ステートメント本体の実行は、一致する *`labeled-statement`* 内またはその後の最初のステートメントで開始されます。 実行は、本文の最後まで、または **`break`** ステートメントによってコントロールが本文の外部に転送するまで続行されます。

通常、 **`switch`** ステートメントは次のように使用します。

```C
switch ( expression )
{
    // declarations
    // . . .
    case constant_expression:
        // statements executed if the expression equals the
        // value of this constant_expression
        break;
    default:
        // statements executed if expression does not equal
        // any case constant_expression
}
```

**`break`** ステートメントを使用して、 **`switch`** ステートメント内の特定のラベル付きステートメントの処理を終了できます。 これは、 **`switch`** ステートメントの最後に分岐します。 **`break`** がない場合、プログラムは次のラベル付きステートメントまで続き、 **`break`** またはステートメントの最後に達するまでステートメントが実行されます。 状況によっては、この継続が望ましい場合もあります。

**`default`** ステートメントは、 *`expression`* の値と等しい **`case`** *`constant-expression`* 値がない場合に実行されます。 **`default`** ステートメントがなく、 **`case`** に一致するものが見つからない場合は、 **`switch`** 本体のステートメントは実行されません。 **`default`** ステートメントは、最大で 1 つだけ指定できます。 **`default`** ステートメントは、最後に存在する必要はありません。 **`switch`** ステートメントの本体の任意の場所に出現できます。 **`case`** または **`default`** ラベルは、 **`switch`** ステートメント内でのみ使用できます。

**`switch`** *`expression`* および **`case`** *`constant-expression`* は整数型である必要があります。 各 **`case`** *`constant-expression`* の値は、ステートメント本体内で一意である必要があります。

**`switch`** ステートメント本体の **`case`** および **`default`** ラベルは、ステートメント本体内のどこで実行が開始されるかが決まる初期テストでのみ重要です。 **`switch`** ステートメントは入れ子にすることができます。 静的変数は、 **`switch`** ステートメントの実行前に初期化されます。

> [!NOTE]
> 宣言は、 **`switch`** の本体を構成する複合ステートメントの先頭に記述できますが、宣言に含まれる初期化は行われません。 **`switch`** ステートメントは、初期化が含まれる行をバイパスして、本体内の実行可能なステートメントに直接制御を移します。

次の例に、 **`switch`** ステートメントを示します。

```C
switch( c )
{
    case 'A':
        capital_a++;
    case 'a':
        letter_a++;
    default :
        total++;
}
```

この例の **`switch`** 本体の 3 つのステートメントは、`c` が `'A'` と等しい場合にすべて実行されます。 **`break`** ステートメントは次の **`case`** の前に出現しないためです。 実行制御は最初のステートメント (`capital_a++;`) に移動し、本体の残りが順に継続されます。 `c` が `'a'` と等しい場合、`letter_a` と `total` がインクリメントされます。 `c` が `'A'` または `'a'` と等しくない場合、`total` のみがインクリメントされます。

```C
switch( i )
{
    case -1:
        n++;
        break;
    case 0 :
        z++;
        break;
    case 1 :
        p++;
        break;
}
```

この例では、 **`break`** ステートメントは **`switch`** 本体の各ステートメントに続きます。 **`break`** ステートメントによって、1 つのステートメントの実行後にステートメント本体を終了することが強制されます。 `i` が -1 と等しい場合、`n` だけがインクリメントされます。 `n++;` ステートメントに続く **`break`** により、残りのステートメントをバイパスして、実行制御をステートメント本体の外部に渡すことが強制されます。 同様に、`i` が 0 と等しい場合は `z` だけがインクリメントされ、`i` が 1 と等しい場合は `p` だけがインクリメントされます。 複合ステートメントの最後に制御は本体の外部に移るため、 **`break`** ステートメントは厳密には必要ありません。 一貫性を持たせるために含まれています。

次の例に示すように、1 つのステートメントに複数の **`case`** ラベルを含めることができます。

```C
switch( c )
{
    case 'a' :
    case 'b' :
    case 'c' :
    case 'd' :
    case 'e' :
    case 'f' :  convert_hex(c);
}
```

この例では、*constant-expression* が `'a'` から `'f'` の間の文字に等しい場合に `convert_hex` 関数が呼び出されます。

### <a name="microsoft-specific"></a>Microsoft 固有の仕様

Microsoft C では、 **`switch`** ステートメントの **`case`** 値の数を制限していません。 この数は、使用できるメモリによってのみ制限されます。 ANSI C では、1 つの **`switch`** ステートメント内に 257 個までの **`case`** ラベルを使用できます。

Microsoft C のdefaultでは、Microsoft 拡張機能が有効になっています。 これらの拡張機能を無効にするには、[/Za](../build/reference/za-ze-disable-language-extensions.md) コンパイラ オプションを使用します。

## <a name="see-also"></a>関連項目

[switch ステートメント (C++)](../cpp/switch-statement-cpp.md)
