---
description: '詳細情報: numpunct_byname クラス'
title: numpunct_byname クラス
ms.date: 11/04/2016
f1_keywords:
- xlocnum/std::numpunct_byname
helpviewer_keywords:
- numpunct_byname class
ms.assetid: 18412924-e085-4771-b5e9-7a200cbdd7c0
ms.openlocfilehash: e4e6352f9f65b2a726acf3f8f5f8ede9bffe54f9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338031"
---
# <a name="numpunct_byname-class"></a>numpunct_byname クラス

派生クラステンプレートは、特定のロケールのファセットとして使用できるオブジェクトを表します。このオブジェクトは、 `numpunct` 数値式およびブール式の書式設定と区切り記号を有効にします。

## <a name="syntax"></a>構文

```cpp
template <class CharType>
class numpunct_byname : public numpunct<Elem> {
public:
    explicit numpunct_byname(
    const char* _Locname,
    size_t _Refs = 0);

    explicit numpunct_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual ~numpunct_byname();

};
```

## <a name="remarks"></a>解説

その動作は [名前付き](../standard-library/locale-class.md#name) のロケールによって決まり `_Locname` ます。 コンストラクターは、 [numpunct](../standard-library/numpunct-class.md#numpunct)() を使用して、その基本オブジェクトを初期化し \<CharType> `_Refs` ます。

## <a name="requirements"></a>要件

**ヘッダー:**\<locale>

**名前空間:** std

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
