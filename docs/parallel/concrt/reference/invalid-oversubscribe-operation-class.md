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
ms.openlocfilehash: a1728053c7b42afedb4cda9b2dc96a089750a866
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2018
ms.locfileid: "49161698"
---
# <a name="invalidoversubscribeoperation-class"></a>invalid_oversubscribe_operation クラス

このクラスは、場合にスローされる例外を表します、`Context::Oversubscribe`メソッドを呼び出すと、`_BeginOversubscription`パラメーターに設定**false**を事前に呼び出さずに、`Context::Oversubscribe`メソッドを`_BeginOversubscription`パラメーターに設定**true**します。

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
