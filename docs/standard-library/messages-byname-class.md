---
title: messages_byname クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xlocmes/std::messages_byname
dev_langs:
- C++
helpviewer_keywords:
- messages_byname class
ms.assetid: c6c64841-3e80-43c8-b54c-fed41833ad6b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e03cb627e7e9db40d56a69112977d87141626696
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "44100445"
---
# <a name="messagesbyname-class"></a>messages_byname クラス

特定のロケールのメッセージ ファセットとして使用できるオブジェクトを表す派生テンプレート クラス。ローカライズされたメッセージを取得できるようにします。

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

*_Locname*<br/>
名前付きのロケール。

*_Refs*<br/>
最初の参照数。

## <a name="remarks"></a>Remarks

名前付きのロケールでその動作が決まります *_Locname*します。 各コンストラクターは、[messages](../standard-library/messages-class.md#messages)\<CharType>( `_Refs`) を使用して、その基本オブジェクトを初期化します。

## <a name="requirements"></a>要件

**ヘッダー:** \<locale>

**名前空間:** std

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
