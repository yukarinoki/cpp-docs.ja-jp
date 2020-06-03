---
title: out_of_memory クラス
ms.date: 11/04/2016
f1_keywords:
- out_of_memory
- AMPRT/out_of_memory
- AMPRT/Concurrency::out_of_memory::out_of_memory
helpviewer_keywords:
- out_of_memory class
ms.assetid: 3aa7e682-8f13-4ae6-9188-31fb423956e4
ms.openlocfilehash: e716d4952bdb9634cc0d195285d3a65c5c06b0a1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336802"
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
|[out_of_memoryコンストラクタ](#ctor)|`out_of_memory` クラスの新しいインスタンスを初期化します。|

## <a name="inheritance-hierarchy"></a>継承階層

`exception`

`runtime_exception`

`out_of_memory`

## <a name="requirements"></a>必要条件

**ヘッダー:** アンパート.h

**名前空間:** Concurrency

## <a name="out_of_memory"></a><a name="ctor"></a>out_of_memory

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

[同時実行名前空間 (C++ AMP)](concurrency-namespace-cpp-amp.md)
