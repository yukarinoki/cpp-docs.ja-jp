---
description: '詳細情報: out_of_memory クラス'
title: out_of_memory クラス
ms.date: 11/04/2016
f1_keywords:
- out_of_memory
- AMPRT/out_of_memory
- AMPRT/Concurrency::out_of_memory::out_of_memory
helpviewer_keywords:
- out_of_memory class
ms.assetid: 3aa7e682-8f13-4ae6-9188-31fb423956e4
ms.openlocfilehash: bb7ba1db5be5921111b1fba2e12ea5cf6a5bea1b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97329928"
---
# <a name="out_of_memory-class"></a>out_of_memory クラス

システムまたはデバイスのメモリ不足のためにメソッドが失敗した場合にスローされる例外。

## <a name="syntax"></a>構文

```cpp
class out_of_memory : public runtime_exception;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[out_of_memory コンストラクター](#ctor)|`out_of_memory` クラスの新しいインスタンスを初期化します。|

## <a name="inheritance-hierarchy"></a>継承階層

`exception`

`runtime_exception`

`out_of_memory`

## <a name="requirements"></a>要件

**ヘッダー:** amprt. h

**名前空間:** Concurrency

## <a name="out_of_memory"></a><a name="ctor"></a> out_of_memory

クラスの新しいインスタンスを初期化します。

### <a name="syntax"></a>構文

```cpp
explicit out_of_memory(
    const char * _Message ) throw();

out_of_memory () throw();
```

### <a name="parameters"></a>パラメーター

*_Message*<br/>
エラーの説明。

### <a name="return-value"></a>戻り値

`out_of_memory` クラスの新しいインスタンス。

## <a name="see-also"></a>関連項目

[Concurrency 名前空間 (C++ AMP)](concurrency-namespace-cpp-amp.md)
