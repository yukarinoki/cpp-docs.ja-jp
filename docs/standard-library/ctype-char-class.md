---
title: ctype&lt;char&gt; クラス
ms.date: 11/04/2016
f1_keywords:
- ctype<char>
- locale/std::ctype<char>
helpviewer_keywords:
- ctype<char> class
ms.assetid: ee30acb4-a743-405e-b3d4-13602092da84
ms.openlocfilehash: d2c74ef46babe388cfa6d649e8b4501b7c235bb9
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220965"
---
# <a name="ctypeltchargt-class"></a>ctype&lt;char&gt; クラス

クラスは、クラステンプレートを型に明示的に特殊化したもの `ctype\<CharType>` **`char`** であり、型の文字のさまざまなプロパティを特徴付けるためにロケールファセットとして使用できるオブジェクトを記述し **`char`** ます。

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

## <a name="remarks"></a>解説

明示的な特殊化は、いくつかの点でクラステンプレートとは異なります。

- クラスのオブジェクトは `ctype<char>` 、ctype マスクテーブルの最初の要素へのポインター、型の UCHAR_MAX + 1 要素の配列を格納 `ctype_base::mask` します。 また、 `operator delete[]` ctype オブジェクトが破棄されたときに、を使用して配列を削除するかどうかを示すブール型オブジェクトも格納し \< **Elem**> ます。

- 唯一のパブリックコンストラクターを使用すると `tab` 、、ctype マスクテーブル、およびを指定でき `del` ます。ブール値オブジェクトは、オブジェクトが破棄されたときに配列が削除される場合は true、 `ctype<char>` 参照カウントパラメーター参照にも指定できます。

- プロテクトメンバー関数は、 `table` 格納されている ctype マスクテーブルを返します。

- 静的メンバーオブジェクトは、 `table_size` ctype マスクテーブル内の要素の最小数を指定します。

- プロテクト静的メンバー関数 `classic_table` ("C" ロケールに適した ctype マスクテーブルを返します。

- 保護されている仮想メンバー関数 [do_is](../standard-library/ctype-class.md#do_is)、[do_scan_is](../standard-library/ctype-class.md#do_scan_is)、[do_scan_not](../standard-library/ctype-class.md#do_scan_not) はありません。 それに対応するパブリック メンバー関数が同等の操作を実行します。

メンバー関数の [do_narrow](../standard-library/ctype-class.md#do_narrow) と [do_widen](../standard-library/ctype-class.md#do_widen) は、要素を変更せずにコピーします。

## <a name="requirements"></a>必要条件

**ヘッダー:**\<locale>

**名前空間:** std

## <a name="see-also"></a>関連項目

[ファセットクラス](locale-class.md#facet_class)\
[ctype_base クラス](../standard-library/ctype-base-class.md)\
[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
