---
description: '詳細情報: ctype_byname クラス'
title: ctype_byname クラス
ms.date: 11/04/2016
f1_keywords:
- xlocale/std::ctype_byname
helpviewer_keywords:
- ctype_byname class
ms.assetid: a5cec021-a1f8-425f-8757-08e6f064b604
ms.openlocfilehash: cc5f44e1c544d2088030621b684c9e070175d695
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97233137"
---
# <a name="ctype_byname-class"></a>ctype_byname クラス

派生クラステンプレートは、特定のロケールの ctype ファセットとして使用できるオブジェクトを記述します。これにより、文字の分類と、大文字と小文字の区別、およびロケールによって指定された文字セットの文字の変換が可能になります。

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

## <a name="remarks"></a>解説

その動作は名前付きのロケール `_Locname` で決まります。 各コンストラクターは、 [ctype](../standard-library/ctype-class.md)() を使用して、 \<CharType> `_Refs` または基底クラスの同等の基本オブジェクトを初期化 `ctype<char>` します。

## <a name="requirements"></a>要件

**ヘッダー:**\<locale>

**名前空間:** std

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
