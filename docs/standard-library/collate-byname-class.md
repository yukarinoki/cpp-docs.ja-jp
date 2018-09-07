---
title: collate_byname クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- locale/std::collate_byname
dev_langs:
- C++
helpviewer_keywords:
- collate_byname class
ms.assetid: 3dc380df-867c-4763-b60e-ba62a8e63ca7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b60e5aebcab11e839b6b1e6168aaac55a0202b7c
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "44110241"
---
# <a name="collatebyname-class"></a>collate_byname クラス

特定のロケールの照合ファセットとして使用できるオブジェクトを表す派生テンプレート クラス。文字列の並べ替え規則に関する文化的領域に固有の情報を取得できるようにします。

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

*_Locname*<br/>
名前付きのロケール。

*_Refs*<br/>
最初の参照数。

## <a name="remarks"></a>Remarks

このテンプレート クラスは、[collate](../standard-library/collate-class.md#collate)\<CharType> 型の[ロケール ファセット](../standard-library/locale-class.md#facet_class)として使用できるオブジェクトを表します。 その動作によって決定されます、[という](../standard-library/locale-class.md#name)ロケール *_Locname*します。 各コンストラクターは、[collate](../standard-library/collate-class.md#collate)\<CharType>( `_Refs`) を使用して、その基本オブジェクトを初期化します。

## <a name="requirements"></a>要件

**ヘッダー:** \<locale>

**名前空間:** std

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
