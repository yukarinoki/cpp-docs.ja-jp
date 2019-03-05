---
title: unsupported_feature クラス
ms.date: 11/04/2016
f1_keywords:
- unsupported_feature
- AMPRT/unsupported_feature
- AMPRT/Concurrency::unsupported_feature
helpviewer_keywords:
- unsupported_feature class
ms.assetid: 6b1ab917-df13-48c7-9648-7cb2465a0ff5
ms.openlocfilehash: 6a742c3fd1965882c3fa72cb1fab985cd4d981d1
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57272543"
---
# <a name="unsupportedfeature-class"></a>unsupported_feature クラス

サポートされていない機能が使用される場合にスローされる例外です。

## <a name="syntax"></a>構文

```
class unsupported_feature : public runtime_exception;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[unsupported_feature コンス トラクター](#ctor)|
  `unsupported_feature` 例外の新しいインスタンスを構築します。|

## <a name="inheritance-hierarchy"></a>継承階層

`exception`

`runtime_exception`

`unsupported_feature`

## <a name="unsupported_feature__ctor"></a> unsupported_feature

  unsupported_feature 例外の新しいインスタンスを構築します。

### <a name="syntax"></a>構文

```
explicit unsupported_feature(
    const char * _Message ) throw();

unsupported_feature() throw();
```

### <a name="parameters"></a>パラメーター

*_Message*<br/>
エラーの説明。

### <a name="return-value"></a>戻り値

`unsupported_feature` オブジェクト。

## <a name="requirements"></a>必要条件

**ヘッダー:** amprt.h

**名前空間:** コンカレンシー

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間 (C++ AMP)](concurrency-namespace-cpp-amp.md)
