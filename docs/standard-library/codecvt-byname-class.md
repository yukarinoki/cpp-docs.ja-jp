---
title: codecvt_byname クラス
ms.date: 11/04/2016
f1_keywords:
- xlocale/std::codecvt_byname
helpviewer_keywords:
- codecvt_byname class
ms.assetid: b63b6c04-f60c-47b9-8e30-a933f24a8ffb
ms.openlocfilehash: 62781d575d6b9dda3f3c1e2a744091221c6f9584
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2019
ms.locfileid: "68459858"
---
# <a name="codecvtbyname-class"></a>codecvt_byname クラス

特定のロケールの照合ファセットとして使用できるオブジェクトを表す派生テンプレート クラス。変換に関する文化的領域に固有の情報を取得できるようにします。

## <a name="syntax"></a>構文

```cpp
template <class CharType, class Byte, class StateType>
class codecvt_byname: public codecvt<CharType, Byte, StateType> {
public:
    explicit codecvt_byname(
    const char* _Locname,
    size_t _Refs = 0);
```

```cpp
explicit codecvt_byname(
    const string& _Locname,
    size_t _Refs = 0);
```

```cpp
protected:
    virtual ~codecvt_byname();

};
```

### <a name="parameters"></a>パラメーター

*名前 (_d)* \
名前付きのロケール。

*参照 (_c)* \
最初の参照数。

## <a name="remarks"></a>Remarks

名前付きのロケールが作成されると、byname ファセットが自動的に作成されます。

その動作は、名前付きロケール*名*によって決まります。 各コンストラクターは、[codecvt](../standard-library/codecvt-class.md)\<CharType, Byte, StateType>( `_Refs`) を使用して、その基本オブジェクトを初期化します。

## <a name="requirements"></a>必要条件

**ヘッダー:** \<locale>

**名前空間:** std

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
