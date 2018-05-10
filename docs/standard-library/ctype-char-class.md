---
title: ctype&lt;char&gt; クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- ctype<char>
- locale/std::ctype<char>
dev_langs:
- C++
helpviewer_keywords:
- ctype<char> class
ms.assetid: ee30acb4-a743-405e-b3d4-13602092da84
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: edbc96419e68cf584222e4008f58fd96169b2fb9
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="ctypeltchargt-class"></a>ctype&lt;char&gt; クラス

`char` 型への **ctype\<CharType**> テンプレート クラスの明示的な特殊化クラス。`char` 型の文字のさまざまなプロパティを設定するロケール ファセットとして使用できるオブジェクトを表します。

## <a name="syntax"></a>構文

```cpp
template <>
class ctype<char>
: public ctype_base
{
public:
    typedef char _Elem;
    typedef _Elem char_type;
    bool is(
    mask _Maskval,
    _Elem _Ch) const;


    const _Elem* is(
    const _Elem* first,
    const _Elem* last,
    mask* dest) const;


    const _Elem* scan_is(
    mask _Maskval,
    const _Elem* first,
    const _Elem* last) const;


    const _Elem* scan_not(
    mask _Maskval,
    const _Elem* first,
    const _Elem* last) const;


    _Elem tolower(
    _Elem _Ch) const;


    const _Elem* tolower(
    _Elem* first,
    const _Elem* last) const;


    _Elem toupper(
    _Elem _Ch) const;


    const _Elem* toupper(
    _Elem* first,
    const _Elem* last) const;


    _Elem widen(
    char _Byte) const;


    const _Elem* widen(
    const char* first,
    const char* last,
    _Elem* dest) const;


    const _Elem* _Widen_s(
    const char* first,
    const char* last,
    _Elem* dest,
    size_t dest_size) const;


    _Elem narrow(
    _Elem _Ch,
    char _Dflt = '\0') const;


    const _Elem* narrow(
    const _Elem* first,
    const _Elem* last,
    char _Dflt,
    char* dest) const;


    const _Elem* _Narrow_s(
    const _Elem* first,
    const _Elem* last,
    char _Dflt,
    char* dest,
    size_t dest_size) const;


    static locale::id& id;
    explicit ctype(
    const mask* _Table = 0,
    bool _Deletetable = false,
    size_t _Refs = 0);

protected:
    virtual ~ctype();
//other protected members
};
```

## <a name="remarks"></a>コメント

明示的な特殊化は、いくつかの点でテンプレート クラスとは異なります。

- クラス ctype< `char`> のオブジェクトは、型 **ctype_base::mask** の UCHAR_MAX + 1 要素の配列である ctype マスク テーブルの最初の要素を示すポインターを格納します。 ctype\< **Elem**> オブジェクトが破棄されるとき、(`operator delete[]` を利用して) 配列を削除するかどうかを示すブール値も格納します。

- その唯一のパブリック コンストラクターでは、**tab**、ctype マスク テーブル、**del**、ctype< `char`> オブジェクトが破棄されるときに配列を削除する場合に true となるブール値オブジェクト、参照数パラメーター参照を指定できます。

- 保護されているメンバー関数 **table** は、格納されている ctype マスク テーブルを返します。

- 静的メンバー オブジェクト **table_size** は、ctype マスク テーブルの最小要素数を指定します。

- 保護されている静的メンバー関数 **classic_table**( は、"C" ロケールに適切な ctype マスク テーブルを返します。

- 保護されている仮想メンバー関数 [do_is](../standard-library/ctype-class.md#do_is)、[do_scan_is](../standard-library/ctype-class.md#do_scan_is)、[do_scan_not](../standard-library/ctype-class.md#do_scan_not) はありません。 それに対応するパブリック メンバー関数が同等の操作を実行します。

メンバー関数の [do_narrow](../standard-library/ctype-class.md#do_narrow) と [do_widen](../standard-library/ctype-class.md#do_widen) は、要素を変更せずにコピーします。

## <a name="requirements"></a>要件

**ヘッダー:** \<locale>

**名前空間:** std

## <a name="see-also"></a>関連項目

[facet クラス](http://msdn.microsoft.com/Library/dd4f12f5-cb1b-457f-af56-2fb204216ec1)<br/>
[ctype_base クラス](../standard-library/ctype-base-class.md)<br/>
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
