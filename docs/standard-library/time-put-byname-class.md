---
title: time_put_byname クラス
ms.date: 11/04/2016
f1_keywords:
- xloctime/std::time_put_byname
helpviewer_keywords:
- time_put_byname class
ms.assetid: e08c2348-64d2-4ace-98b1-1496e14c7b1a
ms.openlocfilehash: ffe7aa276e9380b6544a78c1c1735ab57765507a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50495967"
---
# <a name="timeputbyname-class"></a>time_put_byname クラス

この派生テンプレート クラスは、型 `time_put`\< CharType, OutputIterator > のロケール ファセットとして使用できるオブジェクトを表します。

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

*_Locname*<br/>
ロケール名。

*_Refs*<br/>
最初の参照数。

## <a name="remarks"></a>Remarks

その動作によって決定されます、[という](../standard-library/locale-class.md#name)ロケール *_Locname*します。 各コンス トラクターを使用してその基本オブジェクトを初期化します[time_put](../standard-library/time-put-class.md#time_put)\<CharType, OutputIterator > (`_Refs`)。

## <a name="requirements"></a>必要条件

**ヘッダー:** \<locale>

**名前空間:** std

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
