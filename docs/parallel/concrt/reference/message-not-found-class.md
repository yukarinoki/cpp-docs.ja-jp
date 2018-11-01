---
title: message_not_found クラス
ms.date: 11/04/2016
f1_keywords:
- message_not_found
- CONCRT/concurrency::message_not_found
- CONCRT/concurrency::message_not_found::message_not_found
helpviewer_keywords:
- message_not_found class
ms.assetid: a96b9995-5ad7-4600-83c8-c15e329ff10e
ms.openlocfilehash: 7b6bd33e69d24e452414b2537ad70bf31e6b722f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50458475"
---
# <a name="messagenotfound-class"></a>message_not_found クラス

このクラスは、要求されたメッセージがメッセージング ブロックで見つからない場合にスローされる例外を表します。

## <a name="syntax"></a>構文

```
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

## <a name="requirements"></a>必要条件

**ヘッダー:** concrt.h

**名前空間:** concurrency

##  <a name="ctor"></a> message_not_found

`message_not_found` オブジェクトを構築します。

```
explicit _CRTIMP message_not_found(_In_z_ const char* _Message) throw();

message_not_found() throw();
```

### <a name="parameters"></a>パラメーター

*メッセージ (_m)*<br/>
エラーの説明メッセージ。

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間](concurrency-namespace.md)<br/>
[非同期メッセージ ブロック](../../../parallel/concrt/asynchronous-message-blocks.md)

