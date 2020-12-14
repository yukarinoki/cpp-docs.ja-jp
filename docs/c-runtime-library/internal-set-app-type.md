---
description: '詳細については、次を参照してください: __set_app_type'
title: __set_app_type
ms.date: 11/04/2016
api_name:
- __set_app_type
- _set_app_type
api_location:
- msvcr90.dll
- msvcr100.dll
- msvcr110.dll
- msvcr80.dll
- msvcrt.dll
- msvcr120.dll
- msvcr110_clr0400.dll
- api-ms-win-crt-runtime-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __set_app_type
helpviewer_keywords:
- __set_app_type
ms.assetid: f0ac0f4d-70e6-4e96-9e43-eb9d1515490c
ms.openlocfilehash: 19aafebc4f7fd848804e21193332fb693af56010
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97246765"
---
# <a name="__set_app_type"></a>__set_app_type

現在のアプリケーションの種類を設定します。

## <a name="syntax"></a>構文

```cpp
void __set_app_type (
   int at
   )
```

#### <a name="parameters"></a>パラメーター

*at*<br/>
アプリケーションの種類を示す値。 次の値を指定できます。

|値|説明|
|-----------|-----------------|
|_UNKNOWN_APP|不明なアプリケーションの種類。|
|_CONSOLE_APP|コンソール (コマンドライン) アプリケーション。|
|_GUI_APP|GUI (Windows) アプリケーション。|

## <a name="remarks"></a>解説

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|__set_app_type|internal.h|
