---
description: '詳細情報: context_self_unblock クラス'
title: context_self_unblock クラス
ms.date: 11/04/2016
f1_keywords:
- context_self_unblock
- CONCRT/concurrency::context_self_unblock
- CONCRT/concurrency::context_self_unblock::context_self_unblock
helpviewer_keywords:
- context_self_unblock class
ms.assetid: 9601cd28-4f40-4c2e-89ab-747068956331
ms.openlocfilehash: 51fae67530e2836b92a6ab7a13e2b136f1d438c9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97188977"
---
# <a name="context_self_unblock-class"></a>context_self_unblock クラス

このクラスは、同じコンテキストから `Unblock` オブジェクトの `Context` メソッドが呼び出された場合にスローされる例外を表します。 これは、特定のコンテキストがそれ自体のブロックを解除しようとしたことを示します。

## <a name="syntax"></a>構文

```cpp
class context_self_unblock : public std::exception;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[context_self_unblock](#ctor)|オーバーロードされます。 `context_self_unblock` オブジェクトを構築します。|

## <a name="inheritance-hierarchy"></a>継承階層

`exception`

`context_self_unblock`

## <a name="requirements"></a>要件

**ヘッダー:** concrt .h

**名前空間:** concurrency

## <a name="context_self_unblock"></a><a name="ctor"></a> context_self_unblock

`context_self_unblock` オブジェクトを構築します。

```cpp
explicit _CRTIMP context_self_unblock(_In_z_ const char* _Message) throw();

context_self_unblock() throw();
```

### <a name="parameters"></a>パラメーター

*_Message*<br/>
エラーの説明メッセージ。

## <a name="see-also"></a>関連項目

[concurrency 名前空間](concurrency-namespace.md)
