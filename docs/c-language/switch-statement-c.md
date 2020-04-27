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
ms.openlocfilehash: 12163e85110092e3e372fa496cf42efd7574ea8d
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "82167677"
---
# <a name="opno-locswitch-statement-c"></a>switchステートメント (C)

ステートメント**switch** と**case** ステートメントを使用すると、複雑な条件付き操作および分岐操作を制御できます。 ステートメント**switch** は、本体内のステートメントに制御を移します。

## <a name="syntax"></a>構文

*selection-statement*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`switch (`***式* **`)`** *ステートメント*

*ラベル付き-ステートメント*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`case`**  *定数式*  **`:`**  *ステートメント*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`default :`**  *諸表*

**case** *定数式*が** switch (** *expression* **)** の値と一致するステートメントに制御が渡されます。 ステートメント**switch** には、任意の数**case** のインスタンスを含めることができます。 ただし、同じ**switch** ステートメントcase内の2つの定数を同じ値にすることはできません。 ステートメント本体の実行は、選択したステートメントから開始されます。 この処理は、本文が終了するまで、または**break** ステートメントによってコントロールが本文の外に移動されるまで続行されます。

**switch** ステートメントの使用は、通常、次のようになります。

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

ステートメントを使用**break** すると、ステートメント内**switch** の特定のラベル付きステートメントの処理を終了できます。 **switch** ステートメントの最後に分岐します。 を**break** 指定しない場合、プログラムは、 **break** またはステートメントの最後に到達するまでステートメントを実行して、次にラベルが付けられたステートメントに進みます。 この継続は、状況によっては望ましい場合があります。

**default** **case** *定数式*が** switch (** *expression* **)** の値と等しい場合は、ステートメントが実行されます。 **default** ステートメントが存在せず、一致が**case** 見つからない場合は、 **switch** 本体のステートメントは実行されません。 1つのステートメントだけ**default** を指定できます。 ステートメント**default** は、末尾に配置する必要はありません。 **switch** ステートメントの本体の任意の場所に表示される場合があります。 **case** または**default** ラベルは、 **switch** ステートメント内でのみ使用できます。

**switch** *式*の型と**case** *定数式*は整数でなければなりません。 各**case** *定数式*の値は、ステートメント本体内で一意である必要があります。

ステートメント本体**default** のおよびラベルは、 **case** ステートメント本体での実行の開始位置を決定する初期テストでのみ重要です。 **switch** **switch** ステートメントは入れ子にすることができます。 すべての静的変数は、 **switch** ステートメントを実行する前に初期化されます。

> [!NOTE]
> 宣言は、 **switch** 本体を形成する複合ステートメントの先頭に記述できますが、宣言に含まれる初期化は実行されません。 ステートメント**switch** は、初期化を含む行をバイパスして、本体内の実行可能なステートメントに直接制御を移します。

**switch** ステートメントの例を次に示します。

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

**switch** この例の本体の3つのステートメントは、が`c`に`'A'`等しい場合に実行さ**break** れます。これはcase、次の前にステートメントが存在しないためです。 実行制御は最初のステートメント (`capital_a++;`) に移動し、本体の残りが順に継続されます。 `c` が `'a'` と等しい場合、`letter_a` と `total` がインクリメントされます。 は`total` 、または`c` `'a'`と等しく`'A'`ない場合にのみインクリメントされます。

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

この例では、 **break** ステートメントは**switch** 本体の各ステートメントに従います。 ステートメント**break** は、1つのステートメントが実行された後に、ステートメント本体を強制的に終了します。 `i` が -1 と等しい場合、`n` だけがインクリメントされます。 **break** ステートメント`n++;`を実行すると、ステートメント本体から残りのステートメントをバイパスして、実行制御が渡されます。 同様に、`i` が 0 と等しい場合は `z` だけがインクリメントされ、`i` が 1 と等しい場合は `p` だけがインクリメントされます。 最後**break** のステートメントは厳密には必要ありません。これは、複合ステートメントの最後にコントロールが本文から渡されるためです。 一貫性のために含まれています。

次の例に示すよう**case** に、1つのステートメントに複数のラベルを含めることができます。

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

Microsoft C では、 case **switch** ステートメントの値の数は制限されません。 この数は、使用できるメモリによってのみ制限されます。 ANSI C では、 case **switch** ステートメントで少なくとも257のラベルが許可されている必要があります。

Microsoft default C のは、microsoft 拡張機能が有効になっていることを示しています。 これらの拡張機能を無効にするには、 [/za](../build/reference/za-ze-disable-language-extensions.md)コンパイラオプションを使用します。

## <a name="see-also"></a>関連項目

[switchステートメント (C++)](../cpp/switch-statement-cpp.md)
