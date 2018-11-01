---
title: invalid_operation クラス
ms.date: 11/04/2016
f1_keywords:
- invalid_operation
- CONCRT/concurrency::invalid_operation
- CONCRT/concurrency::invalid_operation::invalid_operation
helpviewer_keywords:
- invalid_operation class
ms.assetid: 26ba07dc-fcdf-44cb-b748-a31d35205b52
ms.openlocfilehash: 594c09ebedd2be55b288a7f31d55930244d80959
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50473971"
---
# <a name="invalidoperation-class"></a>invalid_operation クラス

このクラスは、同時実行ランタイムによってスローされる他の例外の種類によって正確に記述されない無効な操作を実行しようとした場合にスローされる例外を表します。

## <a name="syntax"></a>構文

```
class invalid_operation : public std::exception;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[invalid_operation](#ctor)|オーバーロードされます。 `invalid_operation` オブジェクトを構築します。|

## <a name="remarks"></a>Remarks

通常、この例外がスローされる条件については、それぞれのメソッドにドキュメント化されています。

## <a name="inheritance-hierarchy"></a>継承階層

`exception`

`invalid_operation`

## <a name="requirements"></a>必要条件

**ヘッダー:** concrt.h

**名前空間:** concurrency

##  <a name="ctor"></a> invalid_operation

`invalid_operation` オブジェクトを構築します。

```
explicit _CRTIMP invalid_operation(_In_z_ const char* _Message) throw();

invalid_operation() throw();
```

### <a name="parameters"></a>パラメーター

*メッセージ (_m)*<br/>
エラーの説明メッセージ。

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間](concurrency-namespace.md)
