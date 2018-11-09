---
title: __set_app_type
ms.date: 11/04/2016
apiname:
- __set_app_type
- _set_app_type
apilocation:
- msvcr90.dll
- msvcr100.dll
- msvcr110.dll
- msvcr80.dll
- msvcrt.dll
- msvcr120.dll
- msvcr110_clr0400.dll
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- __set_app_type
helpviewer_keywords:
- __set_app_type
ms.assetid: f0ac0f4d-70e6-4e96-9e43-eb9d1515490c
ms.openlocfilehash: f42ac1c173637cf85d727adf25ebf9079f4cb37c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50457487"
---
# <a name="setapptype"></a>__set_app_type

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

|[値]|説明|
|-----------|-----------------|
|_UNKNOWN_APP|不明なアプリケーションの種類。|
|_CONSOLE_APP|コンソール (コマンドライン) アプリケーション。|
|_GUI_APP|GUI (Windows) アプリケーション。|

## <a name="remarks"></a>コメント

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|__set_app_type|internal.h|