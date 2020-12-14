---
description: '詳細情報: codecvt_byname クラス'
title: codecvt_byname クラス
ms.date: 11/04/2016
f1_keywords:
- xlocale/std::codecvt_byname
helpviewer_keywords:
- codecvt_byname class
ms.assetid: b63b6c04-f60c-47b9-8e30-a933f24a8ffb
ms.openlocfilehash: 526988f46b729e1a3d4ab6892d2c8f1fecba78a4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97234073"
---
# <a name="codecvt_byname-class"></a>codecvt_byname クラス

特定のロケールの collate ファセットとして使用できるオブジェクトを表す派生クラステンプレート。変換に関してカルチャ領域に固有の情報を取得できます。

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

*_Locname*\
名前付きのロケール。

*_Refs*\
最初の参照数。

## <a name="remarks"></a>解説

名前付きのロケールが作成されると、byname ファセットが自動的に作成されます。

その動作は、 *_Locname* 名前付きロケールによって決まります。 各コンストラクターは、 [codecvt](../standard-library/codecvt-class.md)() を使用して、その基本オブジェクトを初期化 \<CharType, Byte, StateType> `_Refs` します。

## <a name="requirements"></a>要件

**ヘッダー:**\<locale>

**名前空間:** std

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
