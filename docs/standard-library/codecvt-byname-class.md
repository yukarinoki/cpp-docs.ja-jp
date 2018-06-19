---
title: codecvt_byname クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xlocale/std::codecvt_byname
dev_langs:
- C++
helpviewer_keywords:
- codecvt_byname class
ms.assetid: b63b6c04-f60c-47b9-8e30-a933f24a8ffb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 48b1d6e93aa929d95032c04a58b5b419ca312f8d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33842795"
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

`_Locname` 名前付きのロケールです。

`_Refs` 初期の参照カウントの場合。

## <a name="remarks"></a>コメント

名前付きのロケールが作成されると、byname ファセットが自動的に作成されます。

その動作は名前付きのロケール `_Locname` で決まります。 各コンストラクターは、[codecvt](../standard-library/codecvt-class.md)\<CharType, Byte, StateType>( `_Refs`) を使用して、その基本オブジェクトを初期化します。

## <a name="requirements"></a>要件

**ヘッダー:** \<locale>

**名前空間:** std

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
