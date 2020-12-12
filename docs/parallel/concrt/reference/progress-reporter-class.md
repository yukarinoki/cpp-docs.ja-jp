---
description: '詳細情報: progress_reporter クラス'
title: progress_reporter クラス
ms.date: 11/04/2016
f1_keywords:
- progress_reporter
- PPLTASKS/concurrency::progress_reporter
- PPLTASKS/concurrency::progress_reporter::progress_reporter
- PPLTASKS/concurrency::progress_reporter::report
helpviewer_keywords:
- progress_reporter class
ms.assetid: b836efab-2d05-4649-b6fa-d15236f1f813
ms.openlocfilehash: 40ae3dba0c804381478d8c32da4425b20a9825d9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97169360"
---
# <a name="progress_reporter-class"></a>progress_reporter クラス

progress reporter クラスは、特定の型の進行状況の通知をレポートできます。 各 progress_reporter オブジェクトが、特定の非同期アクションまたは操作にバインドされます。

## <a name="syntax"></a>構文

```cpp
template<typename _ProgressType>
class progress_reporter;
```

### <a name="parameters"></a>パラメーター

*_ProgressType*<br/>
progress_reporter クラスによって報告される進行状況の各通知のペイロードの種類。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[progress_reporter](#ctor)||

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[report (レポート)](#report)|progress reporter クラスのバインド先となる非同期アクションまたは非同期操作に、進行状況レポートを送信します。|

## <a name="remarks"></a>解説

この種類は、Windows ランタイムアプリでのみ使用できます。

## <a name="inheritance-hierarchy"></a>継承階層

`progress_reporter`

## <a name="requirements"></a>要件

**ヘッダー:** ppltasks.h

**名前空間:** concurrency

## <a name="progress_reporter"></a><a name="ctor"></a> progress_reporter

```cpp
progress_reporter();
```

## <a name="report"></a><a name="report"></a> ポート

progress reporter クラスのバインド先となる非同期アクションまたは非同期操作に、進行状況レポートを送信します。

```cpp
void report(const _ProgressType& val) const;
```

### <a name="parameters"></a>パラメーター

*val*<br/>
進行状況を示す通知によって報告されるペイロード。

## <a name="see-also"></a>関連項目

[concurrency 名前空間](concurrency-namespace.md)
