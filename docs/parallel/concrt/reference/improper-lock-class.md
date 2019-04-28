---
title: improper_lock クラス
ms.date: 11/04/2016
f1_keywords:
- improper_lock
- CONCRT/concurrency::improper_lock
- CONCRT/concurrency::improper_lock::improper_lock
helpviewer_keywords:
- improper_lock class
ms.assetid: 8f494942-7748-4a2a-8de2-23414bfe6346
ms.openlocfilehash: c10a7f302b63c33869425c4e5bddb36a15373ea8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62262594"
---
# <a name="improperlock-class"></a>improper_lock クラス

このクラスは、ロックが正しく取得されなかった場合にスローされる例外を表します。

## <a name="syntax"></a>構文

```
class improper_lock : public std::exception;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[improper_lock](#ctor)|オーバーロードされます。 `improper_lock exception` を構築します。|

## <a name="remarks"></a>Remarks

通常、同じコンテキストで再帰的に再入不可能なロックの取得を試行したときにこの例外がスローされます。

## <a name="inheritance-hierarchy"></a>継承階層

`exception`

`improper_lock`

## <a name="requirements"></a>必要条件

**ヘッダー:** concrt.h

**名前空間:** concurrency

##  <a name="ctor"></a> improper_lock

`improper_lock exception` を構築します。

```
explicit _CRTIMP improper_lock(_In_z_ const char* _Message) throw();

improper_lock() throw();
```

### <a name="parameters"></a>パラメーター

*_Message*<br/>
エラーの説明メッセージ。

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間](concurrency-namespace.md)<br/>
[critical_section クラス](critical-section-class.md)<br/>
[reader_writer_lock クラス](reader-writer-lock-class.md)
