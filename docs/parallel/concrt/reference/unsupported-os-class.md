---
description: '詳細情報: unsupported_os クラス'
title: unsupported_os クラス
ms.date: 11/04/2016
f1_keywords:
- unsupported_os
- CONCRT/concurrency::unsupported_os
- CONCRT/concurrency::unsupported_os::unsupported_os
helpviewer_keywords:
- unsupported_os class
ms.assetid: 6fa57636-341b-4b51-84cc-261d283ff736
ms.openlocfilehash: 1f9ee74db42d2b34c1b4e24a1951d84a442224bc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97188093"
---
# <a name="unsupported_os-class"></a>unsupported_os クラス

このクラスは、サポート外のオペレーティング システムが使用された場合にスローされる例外を表します。

## <a name="syntax"></a>構文

```cpp
class unsupported_os : public std::exception;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[unsupported_os](#ctor)|オーバーロードされます。 `unsupported_os` オブジェクトを構築します。|

## <a name="inheritance-hierarchy"></a>継承階層

`exception`

`unsupported_os`

## <a name="requirements"></a>要件

**ヘッダー:** concrt .h

**名前空間:** concurrency

## <a name="unsupported_os"></a><a name="ctor"></a> unsupported_os

`unsupported_os` オブジェクトを構築します。

### <a name="syntax"></a>構文

```cpp
explicit _CRTIMP unsupported_os(_In_z_ const char* _Message) throw();

unsupported_os() throw();
```

### <a name="parameters"></a>パラメーター

*_Message*<br/>
エラーの説明メッセージ。

## <a name="see-also"></a>関連項目

[concurrency 名前空間](concurrency-namespace.md)
