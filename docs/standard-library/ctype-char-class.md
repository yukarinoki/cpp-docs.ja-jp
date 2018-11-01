---
title: ctype&lt;char&gt; クラス
ms.date: 11/04/2016
f1_keywords:
- ctype<char>
- locale/std::ctype<char>
helpviewer_keywords:
- ctype<char> class
ms.assetid: ee30acb4-a743-405e-b3d4-13602092da84
ms.openlocfilehash: adaad8f76de5b712aea13794ef2d7b9a096fb8ef
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50491993"
---
# <a name="ctypeltchargt-class"></a>ctype&lt;char&gt; クラス

クラスはテンプレート クラスの明示的な特殊化`ctype\<CharType>`入力**char**、型の文字のさまざまなプロパティを設定するロケール ファセットとして使用できるオブジェクトを記述する**char**.

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

## <a name="remarks"></a>Remarks

明示的な特殊化は、いくつかの点でテンプレート クラスとは異なります。

- Ctype クラスのオブジェクト < `char`> ctype マスク テーブルの最初の要素、UCHAR_MAX の配列 + 型の 1 つの要素へのポインターを格納`ctype_base::mask`します。 ctype\< **Elem**> オブジェクトが破棄されるとき、(`operator delete[]` を利用して) 配列を削除するかどうかを示すブール値も格納します。

- その唯一のパブリック コンス トラクターを指定できます`tab`、ctype マスク テーブル、および`del`、配列する場合は true であるブール型のオブジェクトするときは削除、ctype < `char`> 参照カウントと、オブジェクトが破棄される。パラメーターの参照。

- プロテクト メンバー関数`table`格納されている ctype マスク テーブルを返します。

- 静的メンバー オブジェクト`table_size`ctype マスク テーブル内の要素の最小数を指定します。

- 保護されている静的メンバー関数は、 `classic_table`(返します ctype マスク テーブル"C"ロケールに対応します。

- 保護されている仮想メンバー関数 [do_is](../standard-library/ctype-class.md#do_is)、[do_scan_is](../standard-library/ctype-class.md#do_scan_is)、[do_scan_not](../standard-library/ctype-class.md#do_scan_not) はありません。 それに対応するパブリック メンバー関数が同等の操作を実行します。

メンバー関数の [do_narrow](../standard-library/ctype-class.md#do_narrow) と [do_widen](../standard-library/ctype-class.md#do_widen) は、要素を変更せずにコピーします。

## <a name="requirements"></a>必要条件

**ヘッダー:** \<locale>

**名前空間:** std

## <a name="see-also"></a>関連項目

[facet クラス](locale-class.md#facet_class)<br/>
[ctype_base クラス](../standard-library/ctype-base-class.md)<br/>
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
