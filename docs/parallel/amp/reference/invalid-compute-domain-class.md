---
title: invalid_compute_domain クラス
ms.date: 11/04/2016
f1_keywords:
- invalid_compute_domain
- AMPRT/invalid_compute_domain
- AMPRT/Concurrency::invalid_compute_domain::invalid_compute_domain
helpviewer_keywords:
- invalid_compute_domain class
ms.assetid: ac7a7166-8bdb-4db1-8caf-ea129ab5117e
ms.openlocfilehash: 51fcd9e42bc4497131da5adb3dff72efb46537b3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62351720"
---
# <a name="invalidcomputedomain-class"></a>invalid_compute_domain クラス

ランタイムがで指定された計算ドメインを使用してカーネルを起動できない場合にスローされる例外、 [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each)呼び出しサイト。

## <a name="syntax"></a>構文

```
class invalid_compute_domain : public runtime_exception;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[invalid_compute_domain コンス トラクター](#ctor)|`invalid_compute_domain` クラスの新しいインスタンスを初期化します。|

## <a name="inheritance-hierarchy"></a>継承階層

`exception`

`runtime_exception`

`invalid_compute_domain`

## <a name="requirements"></a>必要条件

**ヘッダー:** amprt.h

**名前空間:** コンカレンシー

## <a name="ctor"></a> invalid_compute_domain

クラスの新しいインスタンスを初期化します。

## <a name="syntax"></a>構文

```
explicit invalid_compute_domain(
    const char * _Message ) throw();

invalid_compute_domain() throw();
```

### <a name="parameters"></a>パラメーター

*_Message*<br/>
エラーの説明。

### <a name="return-value"></a>戻り値

`invalid_compute_domain` クラスのインスタンス。

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間 (C++ AMP)](concurrency-namespace-cpp-amp.md)
