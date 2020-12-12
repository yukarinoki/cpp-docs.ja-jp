---
description: '詳細情報: message_not_found クラス'
title: message_not_found クラス
ms.date: 11/04/2016
f1_keywords:
- message_not_found
- CONCRT/concurrency::message_not_found
- CONCRT/concurrency::message_not_found::message_not_found
helpviewer_keywords:
- message_not_found class
ms.assetid: a96b9995-5ad7-4600-83c8-c15e329ff10e
ms.openlocfilehash: c0b098a530768617b2fa2cf52dfe374dc44a2c12
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97169386"
---
# <a name="message_not_found-class"></a>message_not_found クラス

このクラスは、要求されたメッセージがメッセージング ブロックで見つからない場合にスローされる例外を表します。

## <a name="syntax"></a>構文

```cpp
class message_not_found : public std::exception;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[message_not_found](#ctor)|オーバーロードされます。 `message_not_found` オブジェクトを構築します。|

## <a name="inheritance-hierarchy"></a>継承階層

`exception`

`message_not_found`

## <a name="requirements"></a>要件

**ヘッダー:** concrt .h

**名前空間:** concurrency

## <a name="message_not_found"></a><a name="ctor"></a> message_not_found

`message_not_found` オブジェクトを構築します。

```cpp
explicit _CRTIMP message_not_found(_In_z_ const char* _Message) throw();

message_not_found() throw();
```

### <a name="parameters"></a>パラメーター

*_Message*<br/>
エラーの説明メッセージ。

## <a name="see-also"></a>関連項目

[concurrency 名前空間](concurrency-namespace.md)<br/>
[非同期メッセージブロック](../../../parallel/concrt/asynchronous-message-blocks.md)
