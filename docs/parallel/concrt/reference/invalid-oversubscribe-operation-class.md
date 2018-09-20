---
title: invalid_oversubscribe_operation クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- invalid_oversubscribe_operation
- CONCRT/concurrency::invalid_oversubscribe_operation
- CONCRT/concurrency::invalid_oversubscribe_operation::invalid_oversubscribe_operation
dev_langs:
- C++
helpviewer_keywords:
- invalid_oversubscribe_operation class
ms.assetid: 0a9c5f08-d5e6-4ad0-90a9-517472b3ac28
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e62dc4ad1600b2e5cc7f955c4a419d27482bb557
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46433219"
---
# <a name="invalidoversubscribeoperation-class"></a>invalid_oversubscribe_operation クラス

このクラスは、`Context::Oversubscribe` パラメーターが `_BeginOversubscription` に設定された `false` メソッドを事前に呼び出さずに、`Context::Oversubscribe` パラメーターが `_BeginOversubscription` に設定された `true` メソッドを呼び出した場合にスローされる例外を表します。

## <a name="syntax"></a>構文

```
class invalid_oversubscribe_operation : public std::exception;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[invalid_oversubscribe_operation](#ctor)|オーバーロードされます。 `invalid_oversubscribe_operation` オブジェクトを構築します。|

## <a name="inheritance-hierarchy"></a>継承階層

`exception`

`invalid_oversubscribe_operation`

## <a name="requirements"></a>要件

**ヘッダー:** concrt.h

**名前空間:** concurrency

##  <a name="ctor"></a> invalid_oversubscribe_operation

`invalid_oversubscribe_operation` オブジェクトを構築します。

```
explicit _CRTIMP invalid_oversubscribe_operation(_In_z_ const char* _Message) throw();

invalid_oversubscribe_operation() throw();
```

### <a name="parameters"></a>パラメーター

*メッセージ (_m)*<br/>
エラーの説明メッセージ。

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間](concurrency-namespace.md)
