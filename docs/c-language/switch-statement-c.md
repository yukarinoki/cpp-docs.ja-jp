---
title: switchステートメント (C)
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
ms.openlocfilehash: 5858447602a28dcc5573aa3138e869d106b5aa23
ms.sourcegitcommit: 2f9ff2041d70c406df76c5053151192aad3937ea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2020
ms.locfileid: "82587364"
---
# <a name="switch-statement-c"></a>`switch`ステートメント (C)

ステートメント__`switch`__ と__`case`__ ステートメントを使用すると、複雑な条件付き操作および分岐操作を制御できます。 ステートメント__`switch`__ は、本体内のステートメントに制御を移します。

## <a name="syntax"></a>構文

> *`selection-statement`*:<br/>
> &nbsp;&nbsp;&nbsp;&nbsp; __`switch (`__&nbsp;*`expression`* &nbsp;__`)`__&nbsp;*`statement`*

> *`labeled-statement`*:<br/>
> &nbsp;&nbsp;&nbsp;&nbsp; __`case`__&nbsp;*`constant-expression`*&nbsp;__`:`__&nbsp;*`statement`*<br/>
> &nbsp;&nbsp;&nbsp;&nbsp; __`default`__&nbsp;__`:`__&nbsp;*`statement`*

## <a name="remarks"></a>Remarks

ステートメント__`switch`__ を指定すると、の値*`labeled-statement`* に応じて、ステートメント本体で制御が 1 *`expression`* つのステートメントに転送されます。

との*`expression`* 値は、 *`constant-expression`* それぞれ整数型である必要があります。 は*`constant-expression`* 、コンパイル時に明確な定数整数値を持つ必要があります。

値がの*`expression`* 値**`case`** と一致するステートメントに制御が渡されます。 *`constant-expression`* ステートメント__`switch`__ には、任意の数__`case`__ のインスタンスを含めることができます。 ただし、同じ__`switch`__ ステートメント*`constant-expression`* 内の2つの値が同じ値を持つことはできません。 __`switch`__ ステートメント本体の実行は、の最初のステートメントから、または一致*`labeled-statement`* した後に開始されます。 実行は、本文が終了するまで、またはステートメント__`break`__ によって制御が外部に転送されるまで続行されます。

__`switch`__ ステートメントの使用は、通常、次のようになります。

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

ステートメントを使用__`break`__ すると、ステートメント内__`switch`__ の特定のラベル付きステートメントの処理を終了できます。 __`switch`__ ステートメントの最後に分岐します。 を__`break`__ 指定しない場合、プログラムは、 __`break`__ またはステートメントの最後に到達するまでステートメントを実行して、次にラベルが付けられたステートメントに進みます。 この継続は、状況によっては望ましい場合があります。

値__`default`__ がの__`case`__ *`constant-expression`* *`expression`* 値と等しくない場合は、ステートメントが実行されます。 __`default`__ ステートメントが存在せず、一致が__`case`__ 見つからない場合は、 __`switch`__ 本体のステートメントは実行されません。 1つのステートメントだけ__`default`__ を指定できます。 ステートメント__`default`__ は、末尾に配置する必要はありません。 __`switch`__ ステートメントの本体の任意の場所に表示される場合があります。 __`case`__ または__`default`__ ラベルは、 __`switch`__ ステートメント内でのみ使用できます。

__`switch`__ *`expression`* と__`case`__ の*`constant-expression`* 型は整数である必要があります。 各__`case`__ *`constant-expression`* の値は、ステートメント本体内で一意である必要があります。

ステートメント本体__`default`__ のおよびラベルは、 __`case`__ ステートメント本体での実行の開始位置を決定する初期テストでのみ重要です。 __`switch`__ __`switch`__ ステートメントは入れ子にすることができます。 すべての静的変数は、 __`switch`__ ステートメントを実行する前に初期化されます。

> [!NOTE]
> 宣言は、 __`switch`__ 本体を形成する複合ステートメントの先頭に記述できますが、宣言に含まれる初期化は実行されません。 ステートメント__`switch`__ は、初期化を含む行をバイパスして、本体内の実行可能なステートメントに直接制御を移します。

__`switch`__ ステートメントの例を次に示します。

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

__`switch`__ この例の本体の3つのステートメントは、が`c`に`'A'`等しい場合に実行さ__`break`__ れます。これは__`case`__、次の前にステートメントが存在しないためです。 実行制御は最初のステートメント (`capital_a++;`) に移動し、本体の残りが順に継続されます。 `c` が `'a'` と等しい場合、`letter_a` と `total` がインクリメントされます。 は`total` 、または`c` `'a'`と等しく`'A'`ない場合にのみインクリメントされます。

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

この例では、 __`break`__ ステートメントは__`switch`__ 本体の各ステートメントに従います。 ステートメント__`break`__ は、1つのステートメントが実行された後に、ステートメント本体を強制的に終了します。 `i` が -1 と等しい場合、`n` だけがインクリメントされます。 __`break`__ ステートメント`n++;`を実行すると、ステートメント本体から残りのステートメントをバイパスして、実行制御が渡されます。 同様に、`i` が 0 と等しい場合は `z` だけがインクリメントされ、`i` が 1 と等しい場合は `p` だけがインクリメントされます。 最後__`break`__ のステートメントは厳密には必要ありません。これは、複合ステートメントの最後にコントロールが本文から渡されるためです。 一貫性のために含まれています。

次の例に示すよう__`case`__ に、1つのステートメントに複数のラベルを含めることができます。

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

Microsoft C では、 __`case`__ __`switch`__ ステートメントの値の数は制限されません。 この数は、使用できるメモリによってのみ制限されます。 ANSI C では、 __`case`__ __`switch`__ ステートメントで少なくとも257のラベルが許可されている必要があります。

Microsoft default C のは、microsoft 拡張機能が有効になっていることを示しています。 これらの拡張機能を無効にするには、 [/za](../build/reference/za-ze-disable-language-extensions.md)コンパイラオプションを使用します。

## <a name="see-also"></a>関連項目

[switchステートメント (C++)](../cpp/switch-statement-cpp.md)
