---
description: '詳細については、次を参照してください: _set_app_type'
title: _set_app_type
ms.date: 4/2/2020
api_name:
- _set_app_type
- _o__set_app_type
api_location:
- api-ms-win-crt-runtime-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _set_app_type
- corecrt_startup/_set_app_type
ms.assetid: 1e7fe786-b587-4116-8c05-f7d762350100
ms.openlocfilehash: cd04f1c17f7876c08f8eafb4ef77960073fb3f33
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97277103"
---
# <a name="_set_app_type"></a>_set_app_type

アプリがコンソール アプリと GUI アプリのどちらであるかを CRT に知らせるためにスタートアップ時に使用する内部関数です。

## <a name="syntax"></a>構文

```cpp
typedef enum _crt_app_type
{
    _crt_unknown_app,
    _crt_console_app,
    _crt_gui_app
} _crt_app_type;

void __cdecl _set_app_type(
    _crt_app_type appType
    );
```

## <a name="parameters"></a>パラメーター

*appType*<br/>
アプリケーションの種類を示す値。 次の値を指定できます。

|値|説明|
|----------------|-----------------|
|_crt_unknown_app|不明なアプリケーションの種類。|
|_crt_console_app|コンソール (コマンドライン) アプリケーション。|
|_crt_gui_app|GUI (Windows) アプリケーション。|

## <a name="remarks"></a>解説

通常は、この関数を呼び出す必要はありません。 この関数は、アプリ内での `main` の呼び出し前に実行される C のランタイム スタートアップ コードに含まれています。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|_set_app_type|process.h|
