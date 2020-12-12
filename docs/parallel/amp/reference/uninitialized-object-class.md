---
description: '詳細情報: uninitialized_object クラス'
title: uninitialized_object クラス
ms.date: 03/27/2019
f1_keywords:
- uninitialized_object
- AMPRT/uninitialized_object
- AMPRT/Concurrency::uninitialized_object
helpviewer_keywords:
- uninitialized_object class
ms.assetid: 6ae3c4e8-64a6-4511-a158-03be197b63af
ms.openlocfilehash: 4929de9e865492c9fb468f5fac336f67fb307efb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326391"
---
# <a name="uninitialized_object-class"></a>uninitialized_object クラス

初期化されていないオブジェクトが使用される場合にスローされる例外です。

## <a name="syntax"></a>構文

```cpp
class uninitialized_object : public runtime_exception;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[uninitialized_object コンストラクター](#uninitialized_object)|`uninitialized_object` クラスの新しいインスタンスを初期化します。|

## <a name="inheritance-hierarchy"></a>継承階層

`exception`

`runtime_exception`

`uninitialized_object`

## <a name="requirements"></a>要件

**ヘッダー:** amprt. h

**名前空間:** Concurrency

## <a name="uninitialized_object"></a><a name="uninitialized_object"></a> uninitialized_object

`uninitialized_object` 例外の新しいインスタンスを構築します。

### <a name="syntax"></a>構文

```cpp
explicit uninitialized_object(
    const char * _Message ) throw();

uninitialized_object() throw();
```

### <a name="parameters"></a>パラメーター

*_Message*<br/>
エラーの説明。

### <a name="return-value"></a>戻り値

`uninitialized_object`例外オブジェクト。

## <a name="see-also"></a>関連項目

[Concurrency 名前空間 (C++ AMP)](concurrency-namespace-cpp-amp.md)
