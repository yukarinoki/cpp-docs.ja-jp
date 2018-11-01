---
title: unsupported_os クラス
ms.date: 11/04/2016
f1_keywords:
- unsupported_os
- CONCRT/concurrency::unsupported_os
- CONCRT/concurrency::unsupported_os::unsupported_os
helpviewer_keywords:
- unsupported_os class
ms.assetid: 6fa57636-341b-4b51-84cc-261d283ff736
ms.openlocfilehash: a776daf138b5fa2da0426afd38bdf7f67721c199
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50448270"
---
# <a name="unsupportedos-class"></a>unsupported_os クラス

このクラスは、サポート外のオペレーティング システムが使用された場合にスローされる例外を表します。

## <a name="syntax"></a>構文

```
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

## <a name="requirements"></a>必要条件

**ヘッダー:** concrt.h

**名前空間:** concurrency

##  <a name="ctor"></a> unsupported_os

`unsupported_os` オブジェクトを構築します。

```
explicit _CRTIMP unsupported_os(_In_z_ const char* _Message) throw();

unsupported_os() throw();
```

### <a name="parameters"></a>パラメーター

*メッセージ (_m)*<br/>
エラーの説明メッセージ。

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間](concurrency-namespace.md)
