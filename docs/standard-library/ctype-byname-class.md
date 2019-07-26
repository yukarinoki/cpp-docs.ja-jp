---
title: ctype_byname クラス
ms.date: 11/04/2016
f1_keywords:
- xlocale/std::ctype_byname
helpviewer_keywords:
- ctype_byname class
ms.assetid: a5cec021-a1f8-425f-8757-08e6f064b604
ms.openlocfilehash: 0b0f33781cc9f1f54661a44a5434c94316432a45
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2019
ms.locfileid: "68457891"
---
# <a name="ctypebyname-class"></a>ctype_byname クラス

特定のロケールの ctype ファセットとして使用できるオブジェクトを表す派生テンプレート クラス。文字を分類したり、大文字/小文字、ネイティブ、ロケールを指定して文字セットを変換したりできます。

## <a name="syntax"></a>構文

```cpp
template <class _Elem>
class ctype_byname : public ctype<_Elem>
{
public:
    explicit ctype_byname(
    const char* _Locname,
    size_t _Refs = 0);

    explicit ctype_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual __CLR_OR_THIS_CALL ~ctype_byname();

};
```

## <a name="remarks"></a>Remarks

その動作は名前付きのロケール `_Locname` で決まります。 各コンストラクターは、[ctype](../standard-library/ctype-class.md)\<CharType>( `_Refs`) または基底クラス `ctype<char>` の同等物でその基底オブジェクトを初期化します。

## <a name="requirements"></a>必要条件

**ヘッダー:** \<locale>

**名前空間:** std

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
