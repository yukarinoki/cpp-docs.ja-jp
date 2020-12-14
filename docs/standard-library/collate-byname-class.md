---
description: '詳細情報: collate_byname クラス'
title: collate_byname クラス
ms.date: 11/04/2016
f1_keywords:
- locale/std::collate_byname
helpviewer_keywords:
- collate_byname class
ms.assetid: 3dc380df-867c-4763-b60e-ba62a8e63ca7
ms.openlocfilehash: 8e5ee60a2415fe6fede6db387c774151b97396dd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97233956"
---
# <a name="collate_byname-class"></a>collate_byname クラス

特定のロケールの collate ファセットとして使用できるオブジェクトを記述する派生クラステンプレート。文字列の並べ替え規則に関するカルチャ領域に固有の情報を取得できます。

## <a name="syntax"></a>構文

```cpp
template <class CharType>
class collate_byname : public collate<CharType> {
public:
    explicit collate_byname(
    const char* _Locname,
    size_t _Refs = 0);

    explicit collate_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual ~collate_byname();

};
```

### <a name="parameters"></a>パラメーター

*_Locname*\
名前付きのロケール。

*_Refs*\
最初の参照数。

## <a name="remarks"></a>解説

クラステンプレートは、 [collate](../standard-library/collate-class.md#collate)型の[ロケールファセット](../standard-library/locale-class.md#facet_class)として使用できるオブジェクトを表し \<CharType> ます。 その動作は、 *_Locname*[名前付き](../standard-library/locale-class.md#name)ロケールによって決まります。 各コンストラクターは、 [collate](../standard-library/collate-class.md#collate)() を使用して、その基本オブジェクトを初期化 \<CharType> `_Refs` します。

## <a name="requirements"></a>要件

**ヘッダー:**\<locale>

**名前空間:** std

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
