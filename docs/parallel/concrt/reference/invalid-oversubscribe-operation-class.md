---
title: invalid_oversubscribe_operation クラス
ms.date: 11/04/2016
f1_keywords:
- invalid_oversubscribe_operation
- CONCRT/concurrency::invalid_oversubscribe_operation
- CONCRT/concurrency::invalid_oversubscribe_operation::invalid_oversubscribe_operation
helpviewer_keywords:
- invalid_oversubscribe_operation class
ms.assetid: 0a9c5f08-d5e6-4ad0-90a9-517472b3ac28
ms.openlocfilehash: 200743d41c1c45f2a957dba0716dd7aa07e3de76
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57266680"
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

## <a name="requirements"></a>必要条件

**ヘッダー:** concrt.h

**名前空間:** concurrency

##  <a name="ctor"></a> invalid_oversubscribe_operation

`invalid_oversubscribe_operation` オブジェクトを構築します。

```
explicit _CRTIMP invalid_oversubscribe_operation(_In_z_ const char* _Message) throw();

invalid_oversubscribe_operation() throw();
```

### <a name="parameters"></a>パラメーター

*_Message*<br/>
エラーの説明メッセージ。

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間](concurrency-namespace.md)
