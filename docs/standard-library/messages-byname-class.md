---
description: '詳細情報: messages_byname クラス'
title: messages_byname クラス
ms.date: 11/04/2016
f1_keywords:
- xlocmes/std::messages_byname
helpviewer_keywords:
- messages_byname class
ms.assetid: c6c64841-3e80-43c8-b54c-fed41833ad6b
ms.openlocfilehash: 960db9dd411e4ac42f81a0027e91ae1001b7877d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97230524"
---
# <a name="messages_byname-class"></a>messages_byname クラス

派生クラステンプレートは、特定のロケールのメッセージファセットとして使用できるオブジェクトを記述します。これにより、ローカライズされたメッセージを取得できるようになります。

## <a name="syntax"></a>構文

```cpp
template <class CharType>
class messages_byname : public messages<CharType> {
public:
    explicit messages_byname(
    const char *_Locname,
    size_t _Refs = 0);

    explicit messages_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual ~messages_byname();

};
```

### <a name="parameters"></a>パラメーター

*_Locname*\
名前付きのロケール。

*_Refs*\
最初の参照数。

## <a name="remarks"></a>解説

その動作は、 *_Locname* 名前付きロケールによって決まります。 各コンストラクターは、[メッセージ](../standard-library/messages-class.md#messages)() を使用して、その基本オブジェクトを初期化 \<CharType> `_Refs` します。

## <a name="requirements"></a>要件

**ヘッダー:**\<locale>

**名前空間:** std

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
