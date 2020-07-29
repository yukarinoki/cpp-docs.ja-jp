---
title: ':::no-loc(switch)::: ステートメント (C)'
ms.date: 04/25/2020
f1_keywords:
- ':::no-loc(switch):::'
helpviewer_keywords:
- ':::no-loc(switch)::: keyword [C]'
ms.assetid: fbede014-23bd-4ab1-8094-c8d9d9cb963a
no-loc:
- ':::no-loc(switch):::'
- ':::no-loc(case):::'
- ':::no-loc(default):::'
- ':::no-loc(break):::'
ms.openlocfilehash: bdd6885f67728a3c81e395f05c33191156896ad9
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220783"
---
# <a name="no-locswitch-statement-c"></a>`:::no-loc(switch):::` ステートメント (C)

**`:::no-loc(switch):::`** および **`:::no-loc(case):::`** ステートメントを使用すると、複雑な条件付き処理や分岐処理を制御しやすくなります。 **`:::no-loc(switch):::`** ステートメントは、本体内のステートメントに制御を移します。

## <a name="syntax"></a>構文

> *`selection-statement`* :\
> &nbsp;&nbsp;&nbsp;&nbsp; **`:::no-loc(switch)::: (`** &nbsp; *`expression`* &nbsp; **`)`** &nbsp; *`statement`*

> *`labeled-statement`* :\
> &nbsp;&nbsp;&nbsp;&nbsp; **`:::no-loc(case):::`** &nbsp; *`constant-expression`* &nbsp; **`:`** &nbsp; *`statement`* \
> &nbsp;&nbsp;&nbsp;&nbsp; **`:::no-loc(default):::`** &nbsp; **`:`** &nbsp; *`statement`*

## <a name="remarks"></a>Remarks

**`:::no-loc(switch):::`** ステートメントを指定すると、 *`expression`* の値に応じて、ステートメント本体の 1 つの *`labeled-statement`* にコントロールが転送されます。

*`expression`* の値 および各 *`constant-expression`* には整数型を指定する必要があります。 *`constant-expression`* は、コンパイル時に明確な定数の整数値を持つ必要があります。

コントロールは、 *`constant-expression`* 値が *`expression`* の値と一致する **`:::no-loc(case):::`** ステートメントに渡されます。 **`:::no-loc(switch):::`** ステートメントには、任意の数の **`:::no-loc(case):::`** インスタンスを含めることができます。 ただし、同じ **`:::no-loc(switch):::`** ステートメント内で 2 つの *`constant-expression`* 値が同じ値を持つことはできません。 **`:::no-loc(switch):::`** ステートメント本体の実行は、一致する *`labeled-statement`* 内またはその後の最初のステートメントで開始されます。 実行は、本文の最後まで、または **`:::no-loc(break):::`** ステートメントによってコントロールが本文の外部に転送するまで続行されます。

通常、 **`:::no-loc(switch):::`** ステートメントは次のように使用します。

```C
:::no-loc(switch)::: ( expression )
{
    // declarations
    // . . .
    :::no-loc(case)::: constant_expression:
        // statements executed if the expression equals the
        // value of this constant_expression
        :::no-loc(break):::;
    :::no-loc(default)::::
        // statements executed if expression does not equal
        // any :::no-loc(case)::: constant_expression
}
```

**`:::no-loc(break):::`** ステートメントを使用して、 **`:::no-loc(switch):::`** ステートメント内の特定のラベル付きステートメントの処理を終了できます。 これは、 **`:::no-loc(switch):::`** ステートメントの最後に分岐します。 **`:::no-loc(break):::`** がない場合、プログラムは次のラベル付きステートメントまで続き、 **`:::no-loc(break):::`** またはステートメントの最後に達するまでステートメントが実行されます。 状況によっては、この継続が望ましい場合もあります。

**`:::no-loc(default):::`** ステートメントは、 *`expression`* の値と等しい **`:::no-loc(case):::`** *`constant-expression`* 値がない場合に実行されます。 **`:::no-loc(default):::`** ステートメントがなく、 **`:::no-loc(case):::`** に一致するものが見つからない場合は、 **`:::no-loc(switch):::`** 本体のステートメントは実行されません。 **`:::no-loc(default):::`** ステートメントは、最大で 1 つだけ指定できます。 **`:::no-loc(default):::`** ステートメントは、最後に存在する必要はありません。 **`:::no-loc(switch):::`** ステートメントの本体の任意の場所に出現できます。 **`:::no-loc(case):::`** または **`:::no-loc(default):::`** ラベルは、 **`:::no-loc(switch):::`** ステートメント内でのみ使用できます。

**`:::no-loc(switch):::`** *`expression`* および **`:::no-loc(case):::`** *`constant-expression`* は整数型である必要があります。 各 **`:::no-loc(case):::`** *`constant-expression`* の値は、ステートメント本体内で一意である必要があります。

**`:::no-loc(switch):::`** ステートメント本体の **`:::no-loc(case):::`** および **`:::no-loc(default):::`** ラベルは、ステートメント本体内のどこで実行が開始されるかが決まる初期テストでのみ重要です。 **`:::no-loc(switch):::`** ステートメントは入れ子にすることができます。 静的変数は、 **`:::no-loc(switch):::`** ステートメントの実行前に初期化されます。

> [!NOTE]
> 宣言は、 **`:::no-loc(switch):::`** の本体を構成する複合ステートメントの先頭に記述できますが、宣言に含まれる初期化は行われません。 **`:::no-loc(switch):::`** ステートメントは、初期化が含まれる行をバイパスして、本体内の実行可能なステートメントに直接制御を移します。

次の例に、 **`:::no-loc(switch):::`** ステートメントを示します。

```C
:::no-loc(switch):::( c )
{
    :::no-loc(case)::: 'A':
        capital_a++;
    :::no-loc(case)::: 'a':
        letter_a++;
    :::no-loc(default)::: :
        total++;
}
```

この例の **`:::no-loc(switch):::`** 本体の 3 つのステートメントは、`c` が `'A'` と等しい場合にすべて実行されます。 **`:::no-loc(break):::`** ステートメントは次の **`:::no-loc(case):::`** の前に出現しないためです。 実行制御は最初のステートメント (`capital_a++;`) に移動し、本体の残りが順に継続されます。 `c` が `'a'` と等しい場合、`letter_a` と `total` がインクリメントされます。 `c` が `'A'` または `'a'` と等しくない場合、`total` のみがインクリメントされます。

```C
:::no-loc(switch):::( i )
{
    :::no-loc(case)::: -1:
        n++;
        :::no-loc(break):::;
    :::no-loc(case)::: 0 :
        z++;
        :::no-loc(break):::;
    :::no-loc(case)::: 1 :
        p++;
        :::no-loc(break):::;
}
```

この例では、 **`:::no-loc(break):::`** ステートメントは **`:::no-loc(switch):::`** 本体の各ステートメントに続きます。 **`:::no-loc(break):::`** ステートメントによって、1 つのステートメントの実行後にステートメント本体を終了することが強制されます。 `i` が -1 と等しい場合、`n` だけがインクリメントされます。 `n++;` ステートメントに続く **`:::no-loc(break):::`** により、残りのステートメントをバイパスして、実行制御をステートメント本体の外部に渡すことが強制されます。 同様に、`i` が 0 と等しい場合は `z` だけがインクリメントされ、`i` が 1 と等しい場合は `p` だけがインクリメントされます。 複合ステートメントの最後に制御は本体の外部に移るため、 **`:::no-loc(break):::`** ステートメントは厳密には必要ありません。 一貫性を持たせるために含まれています。

次の例に示すように、1 つのステートメントに複数の **`:::no-loc(case):::`** ラベルを含めることができます。

```C
:::no-loc(switch):::( c )
{
    :::no-loc(case)::: 'a' :
    :::no-loc(case)::: 'b' :
    :::no-loc(case)::: 'c' :
    :::no-loc(case)::: 'd' :
    :::no-loc(case)::: 'e' :
    :::no-loc(case)::: 'f' :  convert_hex(c);
}
```

この例では、*constant-expression* が `'a'` から `'f'` の間の文字に等しい場合に `convert_hex` 関数が呼び出されます。

### <a name="microsoft-specific"></a>Microsoft 固有の仕様

Microsoft C では、 **`:::no-loc(switch):::`** ステートメントの **`:::no-loc(case):::`** 値の数を制限していません。 この数は、使用できるメモリによってのみ制限されます。 ANSI C では、1 つの **`:::no-loc(switch):::`** ステートメント内に 257 個までの **`:::no-loc(case):::`** ラベルを使用できます。

Microsoft C の:::no-loc(default):::では、Microsoft 拡張機能が有効になっています。 これらの拡張機能を無効にするには、[/Za](../build/reference/za-ze-disable-language-extensions.md) コンパイラ オプションを使用します。

## <a name="see-also"></a>関連項目

[:::no-loc(switch)::: ステートメント (C++)](../cpp/:::no-loc(switch):::-statement-cpp.md)
