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
ms.openlocfilehash: 09418991e805e494c1d79ef31980bbec66a2e172
ms.sourcegitcommit: ced5ff1431ffbd25b20d106901955532723bd188
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "92135568"
---
# <a name="invalid_compute_domain-class"></a>invalid_compute_domain クラス

この例外は、ランタイムが [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each) 呼び出しサイトで指定された計算ドメインを使用してカーネルを起動できない場合にスローされます。

## <a name="syntax"></a>構文

```cpp
class invalid_compute_domain : public runtime_exception;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[invalid_compute_domain コンストラクター](#ctor)|`invalid_compute_domain` クラスの新しいインスタンスを初期化します。|

## <a name="inheritance-hierarchy"></a>継承階層

`exception`

`runtime_exception`

`invalid_compute_domain`

## <a name="requirements"></a>必要条件

**ヘッダー:** amprt. h

**名前空間:** Concurrency

## <a name="invalid_compute_domain"></a><a name="ctor"></a> invalid_compute_domain

クラスの新しいインスタンスを初期化します。

### <a name="syntax"></a>構文

```cpp
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

[Concurrency 名前空間 (C++ AMP)](concurrency-namespace-cpp-amp.md)
