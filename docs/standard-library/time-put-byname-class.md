---
description: '詳細情報: time_put_byname クラス'
title: time_put_byname クラス
ms.date: 11/04/2016
f1_keywords:
- xloctime/std::time_put_byname
helpviewer_keywords:
- time_put_byname class
ms.assetid: e08c2348-64d2-4ace-98b1-1496e14c7b1a
ms.openlocfilehash: b519b28b7af8f5b54f9150d1d84f68cd6695bc49
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167254"
---
# <a name="time_put_byname-class"></a>time_put_byname クラス

派生クラステンプレートは、型のロケールファセットとして使用できるオブジェクトを表し `time_put` \< CharType, OutputIterator > ます。

## <a name="syntax"></a>構文

```cpp
template <class CharType, class OutIt = ostreambuf_iterator<CharType, char_traits<CharType>>>
class time_put_byname : public time_put<CharType, OutputIterator>
{
public:
    explicit time_put_byname(
    const char* _Locname,
    size_t _Refs = 0);

    explicit time_put_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual ~time_put_byname();

};
```

### <a name="parameters"></a>パラメーター

*_Locname*\
ロケール名。

*_Refs*\
最初の参照数。

## <a name="remarks"></a>解説

その動作は、 *_Locname*[名前付き](../standard-library/locale-class.md#name)ロケールによって決まります。 各コンストラクターは、 [time_put](../standard-library/time-put-class.md#time_put)() を使用して、その基本オブジェクトを初期化 \<CharType, OutputIterator> `_Refs` します。

## <a name="requirements"></a>要件

**ヘッダー:**\<locale>

**名前空間:** std

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
