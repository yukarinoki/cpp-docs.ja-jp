---
title: improper_scheduler_attach クラス
ms.date: 11/04/2016
f1_keywords:
- improper_scheduler_attach
- CONCRT/concurrency::improper_scheduler_attach
- CONCRT/concurrency::improper_scheduler_attach::improper_scheduler_attach
helpviewer_keywords:
- improper_scheduler_attach class
ms.assetid: 5a76da0a-091b-4748-8f62-b3a28f674f9e
ms.openlocfilehash: 2d6a7b53269d305c976bcc596fe85dc018442332
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57271542"
---
# <a name="improperschedulerattach-class"></a>improper_scheduler_attach クラス

このクラスは、現在のコンテキストに既にアタッチされている `Attach` オブジェクトで `Scheduler` メソッドが呼び出された場合にスローされる例外を表します。

## <a name="syntax"></a>構文

```
class improper_scheduler_attach : public std::exception;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[improper_scheduler_attach](#ctor)|オーバーロードされます。 
  `improper_scheduler_attach` オブジェクトを構築します。|

## <a name="inheritance-hierarchy"></a>継承階層

`exception`

`improper_scheduler_attach`

## <a name="requirements"></a>必要条件

**ヘッダー:** concrt.h

**名前空間:** concurrency

##  <a name="ctor"></a> improper_scheduler_attach


  `improper_scheduler_attach` オブジェクトを構築します。

```
explicit _CRTIMP improper_scheduler_attach(_In_z_ const char* _Message) throw();

improper_scheduler_attach() throw();
```

### <a name="parameters"></a>パラメーター

*_Message*<br/>
エラーの説明メッセージ。

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間](concurrency-namespace.md)<br/>
[Scheduler クラス](scheduler-class.md)
