---
description: '詳細情報: invalid_operation クラス'
title: invalid_operation クラス
ms.date: 11/04/2016
f1_keywords:
- invalid_operation
- CONCRT/concurrency::invalid_operation
- CONCRT/concurrency::invalid_operation::invalid_operation
helpviewer_keywords:
- invalid_operation class
ms.assetid: 26ba07dc-fcdf-44cb-b748-a31d35205b52
ms.openlocfilehash: f3050d487f2c374f66f264b6e568fce5244d25ba
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334546"
---
# <a name="invalid_operation-class"></a>invalid_operation クラス

このクラスは、コンカレンシー ランタイムによってスローされる他の例外の種類によって正確に記述されない無効な操作を実行しようとした場合にスローされる例外を表します。

## <a name="syntax"></a>構文

```cpp
class invalid_operation : public std::exception;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[invalid_operation](#ctor)|オーバーロードされます。 `invalid_operation` オブジェクトを構築します。|

## <a name="remarks"></a>解説

通常、この例外がスローされる条件については、それぞれのメソッドにドキュメント化されています。

## <a name="inheritance-hierarchy"></a>継承階層

`exception`

`invalid_operation`

## <a name="requirements"></a>要件

**ヘッダー:** concrt .h

**名前空間:** concurrency

## <a name="invalid_operation"></a><a name="ctor"></a> invalid_operation

`invalid_operation` オブジェクトを構築します。

```cpp
explicit _CRTIMP invalid_operation(_In_z_ const char* _Message) throw();

invalid_operation() throw();
```

### <a name="parameters"></a>パラメーター

*_Message*<br/>
エラーの説明メッセージ。

## <a name="see-also"></a>関連項目

[concurrency 名前空間](concurrency-namespace.md)
