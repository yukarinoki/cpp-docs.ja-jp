---
description: '詳細情報: invalid_oversubscribe_operation クラス'
title: invalid_oversubscribe_operation クラス
ms.date: 11/04/2016
f1_keywords:
- invalid_oversubscribe_operation
- CONCRT/concurrency::invalid_oversubscribe_operation
- CONCRT/concurrency::invalid_oversubscribe_operation::invalid_oversubscribe_operation
helpviewer_keywords:
- invalid_oversubscribe_operation class
ms.assetid: 0a9c5f08-d5e6-4ad0-90a9-517472b3ac28
ms.openlocfilehash: 435e3ce0eba29188711c51aa9253060fc08ac62c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334532"
---
# <a name="invalid_oversubscribe_operation-class"></a>invalid_oversubscribe_operation クラス

このクラスは、パラメーターが `Context::Oversubscribe` `_BeginOversubscription` に設定され **`false`** たメソッドを前に呼び出すことなく、パラメーターをに設定してメソッドを呼び出した場合にスローされる例外を表し `Context::Oversubscribe` `_BeginOversubscription` **`true`** ます。

## <a name="syntax"></a>構文

```cpp
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

**ヘッダー:** concrt .h

**名前空間:** concurrency

## <a name="invalid_oversubscribe_operation"></a><a name="ctor"></a> invalid_oversubscribe_operation

`invalid_oversubscribe_operation` オブジェクトを構築します。

```cpp
explicit _CRTIMP invalid_oversubscribe_operation(_In_z_ const char* _Message) throw();

invalid_oversubscribe_operation() throw();
```

### <a name="parameters"></a>パラメーター

*_Message*<br/>
エラーの説明メッセージ。

## <a name="see-also"></a>関連項目

[concurrency 名前空間](concurrency-namespace.md)
