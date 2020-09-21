---
title: time_get_byname クラス
ms.date: 11/04/2016
f1_keywords:
- xloctime/std::time_get_byname
helpviewer_keywords:
- time_get_byname class
ms.assetid: 6e54153e-da40-4bb9-a942-1a6ce57b30c9
ms.openlocfilehash: 040d140fa4250ad33e20d1c2724b6f563e865e6b
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2020
ms.locfileid: "90742659"
---
# <a name="time_get_byname-class"></a>time_get_byname クラス

派生クラステンプレートは、型のロケールファセットとして使用できるオブジェクトを表し `time_get` \<CharType, InputIterator> ます。

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

*_Locname*\
名前付きのロケール。

*_Refs*\
最初の参照数。

## <a name="requirements"></a>必要条件

その動作は、 *_Locname*名前付きロケールによって決まります。 各コンストラクターは、 [time_get](../standard-library/time-get-class.md#time_get)() を使用して、その基本オブジェクトを初期化 \<CharType, InputIterator> `_Refs` します。

**ヘッダー:**\<locale>

**名前空間:** std

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
