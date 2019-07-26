---
title: time_get_byname クラス
ms.date: 11/04/2016
f1_keywords:
- xloctime/std::time_get_byname
helpviewer_keywords:
- time_get_byname class
ms.assetid: 6e54153e-da40-4bb9-a942-1a6ce57b30c9
ms.openlocfilehash: b466f8a893a14f7a94ee7b9e54b72e43aa6cf6e3
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2019
ms.locfileid: "68460025"
---
# <a name="timegetbyname-class"></a>time_get_byname クラス

この派生テンプレート クラスは、型 `time_get`\<CharType, InputIterator> のロケール ファセットとして使用できるオブジェクトを表します。

## <a name="syntax"></a>構文

```cpp
template <class Elem, class InputIterator =
    istreambuf_iterator<CharType, char_traits<CharType>>>
class time_get_byname : public time_get<CharType, InputIterator>
{
public:
    explicit time_get_byname(
    const char* _Locname,
    size_t _Refs = 0);

    explicit time_get_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual ~time_get_byname()
};
```

### <a name="parameters"></a>パラメーター

*名前 (_d)* \
名前付きのロケール。

*参照 (_c)* \
最初の参照数。

## <a name="requirements"></a>必要条件

その動作は、名前付きロケール*名*によって決まります。 各コンストラクターは、[time_get](../standard-library/time-get-class.md#time_get)\<CharType, InputIterator>( `_Refs`) を使用して、その基本オブジェクトを初期化します。

## <a name="requirements"></a>必要条件

**ヘッダー:** \<locale>

**名前空間:** std

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
