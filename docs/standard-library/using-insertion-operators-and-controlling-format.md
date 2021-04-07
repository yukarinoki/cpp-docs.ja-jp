---
description: 詳細については、「挿入演算子と制御形式の使用」を参照してください。
title: 挿入演算子と制御形式の使用
ms.date: 11/04/2016
helpviewer_keywords:
- insertion operators
ms.assetid: cdefe986-6548-4cd1-8a67-b431d7d36a1c
ms.openlocfilehash: 1e5098beb7ff3c83439780c2dc3f908f7fec946a
ms.sourcegitcommit: a89eac9acdbd54a181e3bd5d5bc71a3ef3c1abca
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2021
ms.locfileid: "106506001"
---
# <a name="using-insertion-operators-and-controlling-format"></a>挿入演算子と制御形式の使用

このトピックでは、独自のクラスに対して書式を制御する方法と挿入演算子を作成する方法について説明します。 **`<<`** すべての標準 C++ データ型のあらかじめプログラミングである挿入 () 演算子は、出力ストリームオブジェクトにバイトを送信します。 挿入演算子は定義済み "マニピュレーター" と共に機能します。マニピュレーターとは、整数引数の既定の書式を変更する要素です。

次のオプションを使用して、書式を制御できます。

- [出力幅](#vclrfoutputwidthanchor3)

- [配置](#vclrfalignmentanchor4)

- [[精度]](#vclrfprecisionanchor5)

- [ベース](#vclrfradixanchor6)

## <a name="output-width"></a><a name="vclrfoutputwidthanchor3"></a> 出力幅

出力を配置するには、マニピュレーターをストリームに配置するか、 `setw` メンバー関数を呼び出すことによって、各項目の出力幅を指定し `width` ます。 この例では、列に値を 10 文字の幅に右揃えで出力します。

```cpp
// output_width.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main( )
{
   double values[] = { 1.23, 35.36, 653.7, 4358.24 };
   for( int i = 0; i < 4; i++ )
   {
      cout.width(10);
      cout << values[i] << '\n';
   }
}
```

```Output
      1.23
     35.36
     653.7
   4358.24
```

10 文字の幅に満たない値に対しては先頭に空白文字が追加されます。

フィールドを埋め込むには、 `fill` メンバー関数を使用します。この関数は、幅が指定されているフィールドの埋め込み文字の値を設定します。 既定では、空白文字です。 アスタリスクを使用して数値の列を埋め込むには、前のループを次のように変更し **`for`** ます。

```cpp
for (int i = 0; i <4; i++)
{
    cout.width(10);
    cout.fill('*');
    cout << values[i] << endl;
}
```

`endl` マニピュレーターは、改行文字 (`'\n'`) を置換します。 出力は次のようになります。

```Output
******1.23
*****35.36
*****653.7
***4358.24
```

同じ行のデータ要素に幅を指定するには、`setw` マニピュレーターを使用します。

```cpp
// setw.cpp
// compile with: /EHsc
#include <iostream>
#include <iomanip>
using namespace std;

int main( )
{
   double values[] = { 1.23, 35.36, 653.7, 4358.24 };
   char *names[] = { "Zoot", "Jimmy", "Al", "Stan" };
   for( int i = 0; i < 4; i++ )
      cout << setw( 7 )  << names[i]
           << setw( 10 ) << values[i] << endl;
}
```

`width`メンバー関数はで宣言されて `<iostream>` います。 `setw`または引数を伴う他のマニピュレーターを使用する場合は、を含める必要があり `<iomanip>` ます。 出力では、文字列は 6 桁の幅のフィールドに、整数は 10 桁の幅のフィールドに出力されます。

```Output
   Zoot      1.23
  Jimmy     35.36
     Al     653.7
   Stan   4358.24
```

`setw`または `width` 値の切り捨てを行いません。 書式付き出力がこの幅を超えた場合、ストリームの精度の設定に従い、値全体が出力されます。 `setw`と `width` は、次のフィールドのみに影響します。 フィールドが 1 つ出力されると、フィールドの幅は既定の動作 (既定の幅) に戻ります。 ただし、その他のストリームの形式オプションは変更されるまで有効です。

## <a name="alignment"></a><a name="vclrfalignmentanchor4"></a> 配置

出力ストリームは、既定で右揃えのテキストになります。 前の例の名前を左揃えにし、数値を右揃えにするには、次のようにループを置き換え **`for`** ます。

```cpp
for (int i = 0; i <4; i++)
    cout << setiosflags(ios::left)
         << setw(6) << names[i]
         << resetiosflags(ios::left)
         << setw(10) << values[i] << endl;
```

出力は次のようになります。

```Output
Zoot        1.23
Jimmy      35.36
Al         653.7
Stan     4358.24
```

左揃えのフラグは、マニピュレーターと列挙子を使用して設定し [`setiosflags`](../standard-library/iomanip-functions.md#setiosflags) `left` ます。 この列挙子はクラスで定義されているので、 [`ios`](../standard-library/basic-ios-class.md) その参照にプレフィックスを含める必要があり **`ios::`** ます。 [`resetiosflags`](../standard-library/iomanip-functions.md#resetiosflags)マニピュレーターは左揃えのフラグをオフにします。 ととは異なり `width` `setw` 、との効果 `setiosflags` `resetiosflags` は永続的です。

## <a name="precision"></a><a name="vclrfprecisionanchor5"></a> 精度

浮動小数点の精度の既定値は、6 桁です。 たとえば、3466.9768 という数値は 3466.98 と出力されます。 この値の印刷方法を変更するには、マニピュレーターを使用し [`setprecision`](../standard-library/iomanip-functions.md#setprecision) ます。 マニピュレーターには、との2つのフラグがあり [`fixed`](../standard-library/ios-functions.md#fixed) [`scientific`](../standard-library/ios-functions.md#scientific) ます。 [`fixed`](../standard-library/ios-functions.md#fixed)が設定されている場合、数値は3466.976800 として出力されます。 `scientific`が設定されている場合は、3.4669773 + 003 として出力されます。

1 [つの有意](#vclrfalignmentanchor4) な桁と共に表示される浮動小数点数を表示するには、次のようにループを置き換え **`for`** ます。

```cpp
for (int i = 0; i <4; i++)
    cout << setiosflags(ios::left)
         << setw(6)
         << names[i]
         << resetiosflags(ios::left)
         << setw(10)
         << setprecision(1)
         << values[i]
         << endl;
```

プログラムは次のようにリストを出力します。

```Output
Zoot          1
Jimmy     4e+01
Al        7e+02
Stan      4e+03
```

指数表記を削除するには、ループの前に次のステートメントを挿入し **`for`** ます。

```cpp
cout << setiosflags(ios::fixed);
```

固定小数点表記では、小数点以下 1 桁まで出力されます。

```Output
Zoot         1.2
Jimmy       35.4
Al         653.7
Stan      4358.2
```

フラグをに変更すると `ios::fixed` 、プログラムによって次のように `ios::scientific` 出力されます。

```cpp
Zoot    1.2e+00
Jimmy   3.5e+01
Al      6.5e+02
Stan    4.4e+03
```

この場合も、小数点以下 1 桁まで出力されます。 または `ios::fixed` が設定されている場合 `ios::scientific` 、有効桁数の値によって小数点の後の桁数が決まります。 どちらのフラグも設定されていない場合、精度の値は、全体の有効桁数を決定します。 `resetiosflags` マニピュレーターは、これらのフラグをオフにします。

## <a name="radix"></a><a name="vclrfradixanchor6"></a> ベース

`dec`、 `oct` 、およびマニピュレーターは、 `hex` 入力と出力の既定の基数を設定します。 たとえば、マニピュレーターを出力ストリームに挿入すると、 `hex` オブジェクトは整数の内部データ表現を16進数の出力形式に正しく変換します。 数値は、フラグがクリア (既定値) の場合、a ~ f の数字で小文字で表示されます [`uppercase`](../standard-library/ios-functions.md#uppercase) 。それ以外の場合は、大文字で表示されます。 既定の基数は `dec` (decimal) です。

## <a name="quoted-strings-c14"></a>引用符で囲まれた文字列 (C++14)

ストリームに文字列を挿入すると、メンバー関数を呼び出すことにより、同じ文字列を簡単に取得でき `stringstream::str()` ます。 ただし、抽出演算子を使用して後でストリームを新しい文字列に挿入する場合、 `>>` 既定では最初の空白文字が見つかったときに演算子が停止するため、予期しない結果が発生することがあります。

```cpp
std::stringstream ss;
std::string inserted = "This is a sentence.";
std::string extracted;

ss << inserted;
ss >> extracted;

std::cout << inserted;     //  This is a sentence.
std::cout << extracted;    //  This
```

この動作は手動で克服できますが、文字列のラウンド トリップをより簡単に行うために、C++14 では、`<iomanip>` に `std::quoted` ストリーム マニピュレーターが追加されます。 `quoted()` は、挿入時に文字列を区切り記号 (既定では二重引用符 (")) で囲み、抽出時に終わりの区切り記号までのすべての文字を抽出するストリームを操作します。 埋め込まれた引用符は、エスケープ文字 (既定では '\\\\') でエスケープされます。

区切り記号はストリームオブジェクト内にのみ存在します。抽出された文字列には存在しませんが、によって返される文字列に含まれてい [`basic_stringstream::str`](../standard-library/basic-stringstream-class.md#str) ます。

挿入演算子と抽出演算子の空白の処理は、コード内での文字列の表記方法に依存しません。そのため、入力文字列が未加工の文字列リテラルであるか、標準の文字列であるかにかかわらず、quoted 演算子は便利です。 入力文字列は、その形式にかかわらず、引用符、改行、タブなどを埋め込むことができ、これらすべてがマニピュレーターによって保持され `quoted()` ます。

詳細および完全なコード例については、「」を参照してください [`quoted`](../standard-library/iomanip-functions.md#quoted) 。

## <a name="see-also"></a>関連項目

[出力ストリーム](../standard-library/output-streams.md)
