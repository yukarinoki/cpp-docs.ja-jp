---
title: '&lt;ロケール&gt;|Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- <locale>
- locale/std::<locale>
- std::<locale>
dev_langs:
- C++
helpviewer_keywords:
- locale header
ms.assetid: ca56f9d2-7128-44da-8df1-f4c78c17fbf2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b81483b21f42f17320cb6d7b636fe5dd1f4c5e73
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33859294"
---
# <a name="ltlocalegt"></a>&lt;locale&gt;

文字分類と文字列の照合順序の国際化サポートを含む、数値、通貨、暦のデータの表示や書式設定に関するさまざまな文化的慣習をカプセル化および操作するために、C++ プログラムで使用できるテンプレート クラスおよび関数を定義します。

## <a name="syntax"></a>構文

```cpp
#include <locale>

```

### <a name="functions"></a>関数

|関数|説明|
|-|-|
|[has_facet](../standard-library/locale-functions.md#has_facet)|特定のファセットが指定されたロケールに格納されているかどうかをテストします。|
|[isalnum](../standard-library/locale-functions.md#isalnum)|ロケールの要素が英字または数字であるかどうかをテストします。|
|[isalpha](../standard-library/locale-functions.md#isalpha)|ロケールの要素が英字であるかどうかをテストします。|
|[iscntrl](../standard-library/locale-functions.md#iscntrl)|ロケールの要素が制御文字であるかどうかをテストします。|
|[isdigit](../standard-library/locale-functions.md#isdigit)|ロケールの要素が数字であるかどうかをテストします。|
|[isgraph](../standard-library/locale-functions.md#isgraph)|ロケールの要素が英字または句読点であるかどうかをテストします。|
|[islower](../standard-library/locale-functions.md#islower)|ロケールの要素が小文字であるかどうかをテストします。|
|[isprint](../standard-library/locale-functions.md#isprint)|ロケールの要素が印刷可能な文字であるかどうかをテストします。|
|[ispunct](../standard-library/locale-functions.md#ispunct)|ロケールの要素が句読点であるかどうかをテストします。|
|[isspace](../standard-library/locale-functions.md#isspace)|ロケールの要素が空白文字であるかどうかをテストします。|
|[isupper](../standard-library/locale-functions.md#isupper)|ロケールの要素が大文字であるかどうかをテストします。|
|[isxdigit](../standard-library/locale-functions.md#isxdigit)|ロケールの要素が 16 進数を表すために使用される文字であるかどうかをテストします。|
|[tolower](../standard-library/locale-functions.md#tolower)|文字を小文字に変換します。|
|[toupper](../standard-library/locale-functions.md#toupper)|文字を大文字に変換します。|
|[use_facet](../standard-library/locale-functions.md#use_facet)|ロケールに格納されている指定された型のファセットへの参照を返します。|

### <a name="classes"></a>クラス

|クラス|説明|
|-|-|
|[codecvt](../standard-library/codecvt-class.md)|内部と外部の文字エンコーディングの変換に使用されるファセットを提供するテンプレート クラス。|
|[codecvt_base](../standard-library/codecvt-base-class.md)|変換の結果を示すためにファセットのメンバー関数の戻り値の型として使用される、**result** と呼ばれる列挙型を定義するために使用される codecvt クラスの基底クラス。|
|[codecvt_byname](../standard-library/codecvt-byname-class.md)|特定のロケールの照合ファセットとして使用できるオブジェクトを表す派生テンプレート クラス。変換に関する文化的領域に固有の情報を取得できるようにします。|
|[collate](../standard-library/collate-class.md)|文字列の並べ替え規則を処理するためのファセットを提供する照合テンプレート クラス。|
|[collate_byname](../standard-library/collate-byname-class.md)|特定のロケールの照合ファセットとして使用できるオブジェクトを表す派生テンプレート クラス。文字列の並べ替え規則に関する文化的領域に固有の情報を取得できるようにします。|
|[ctype](../standard-library/ctype-class.md)|文字の分類、大文字と小文字の変換、およびネイティブ文字セットとロケールで使用される文字セットとの変換に使用されるファセットを提供するテンプレート クラス。|
|[ctype\<char>](../standard-library/ctype-char-class.md)|テンプレート クラスの明示的な特殊化クラス**ctype\<CharType**> を入力する`char`型の文字のさまざまなプロパティを表すロケール ファセットとして使用できるオブジェクトを記述します。`char`|
|[ctype_base](../standard-library/ctype-base-class.md)|個々の文字または範囲全体の文字を分類またはテストするための列挙型を定義するために使用される ctype クラスの基底クラス。|
|[ctype_byname](../standard-library/ctype-byname-class.md)|特定のロケールの ctype ファセットとして使用できるオブジェクトを表す派生テンプレート クラス。文字の分類や、大文字と小文字およびネイティブと指定されたロケールの文字セットでの文字の変換を実行できるようにします。|
|[locale](../standard-library/locale-class.md)|特定のローカライズされた環境を集合的に定義する一連のファセットとして、カルチャ固有の情報をカプセル化するロケール オブジェクトを表すクラス。|
|[messages](../standard-library/messages-class.md)|このテンプレート クラスは、特定のロケールの国際化メッセージのカタログからローカライズされたメッセージを取得するためにロケールのファセットとして使用できるオブジェクトを表します。|
|[messages_base](../standard-library/messages-base-class.md)|メッセージのカタログの `int` 型を表す基底クラス。|
|[messages_byname](../standard-library/messages-byname-class.md)|特定のロケールのメッセージ ファセットとして使用できるオブジェクトを表す派生テンプレート クラス。ローカライズされたメッセージを取得できるようにします。|
|[money_base](../standard-library/money-base-class.md)|個々の文字または範囲全体の文字を分類またはテストするための列挙型を定義するために使用される ctype クラスの基底クラス。|
|[money_get](../standard-library/money-get-class.md)|型のシーケンスの変換を制御するロケール ファセットとして使用できるオブジェクトを表すテンプレート クラス**CharType**通貨値にします。|
|[money_put](../standard-library/money-put-class.md)|コントロールへの変換を通貨値を型のシーケンスにロケール ファセットとして使用できるオブジェクトを表すテンプレート クラス**CharType**です。|
|[moneypunct](../standard-library/moneypunct-class.md)|型のシーケンスを記述するためにロケール ファセットとして使用できるオブジェクトを表すテンプレート クラス**CharType**通貨入力フィールドまたは通貨出力フィールドを表すために使用します。|
|[moneypunct_byname](../standard-library/moneypunct-byname-class.md)|特定のロケールの moneypunct ファセットとして使用できるオブジェクトを表す派生テンプレート クラス。通貨の入力または出力フィールドを書式設定できるようにします。|
|[num_get](../standard-library/num-get-class.md)|型のシーケンスの変換を制御するロケール ファセットとして使用できるオブジェクトを表すテンプレート クラス**CharType**に数値を指定します。|
|[num_put](../standard-library/num-put-class.md)|コントロールへの変換を数値型のシーケンスにロケール ファセットとして使用できるオブジェクトを表すテンプレート クラス**CharType**です。|
|[numpunct](../standard-library/numpunct-class.md)|型のシーケンスを表すロケール ファセットとして使用できるオブジェクトを表すテンプレート クラス**CharType**書式設定および数値とブール式の区切りに関する情報を表すために使用します。|
|[numpunct_byname](../standard-library/numpunct-byname-class.md)|特定のロケールの moneypunct ファセットとして使用できるオブジェクトを表す派生テンプレート クラス。数値とブール式の書式設定および区切りを有効にします。|
|[time_base](../standard-library/time-base-class.md)|time_get テンプレート クラスのファセットの基底クラスとして使用されるクラス。dateorder 列挙型とこの方の複数の定数のみを定義します。|
|[time_get](../standard-library/time-get-class.md)|型のシーケンスの変換を制御するロケール ファセットとして使用できるオブジェクトを表すテンプレート クラス**CharType**時刻の値にします。|
|[time_get_byname](../standard-library/time-get-byname-class.md)|型 time_get のロケール ファセットとして使用できるオブジェクトを表す派生テンプレート クラス\<**CharType**、 **InputIterator**>。|
|[time_put](../standard-library/time-put-class.md)|コントロールへの変換を時刻の値型のシーケンスにロケール ファセットとして使用できるオブジェクトを表すテンプレート クラス**CharType**です。|
|[time_put_byname](../standard-library/time-put-byname-class.md)|型のロケール ファセットとして使用できるオブジェクトを表す派生テンプレート クラス`time_put` \< **CharType**、 **OutputIterator**>。|
|[wbuffer_convert クラス](../standard-library/wbuffer-convert-class.md)|バイト ストリーム バッファーとの間の要素の転送を制御するストリーム バッファーを説明します。|
|[wstring_convert クラス](../standard-library/wstring-convert-class.md)|ワイド文字列とバイト文字列間の変換を実行するテンプレート クラス。|

## <a name="see-also"></a>関連項目

[コード ページ](../c-runtime-library/code-pages.md)<br/>
[ロケール名、言語、および国/地域識別文字列](../c-runtime-library/locale-names-languages-and-country-region-strings.md)<br/>
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
