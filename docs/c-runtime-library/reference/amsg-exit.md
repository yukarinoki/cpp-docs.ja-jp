---
description: '詳細については、次を参照してください: _amsg_exit'
title: _amsg_exit
ms.date: 11/04/2016
api_name:
- _amsg_exit
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _amsg_exit
helpviewer_keywords:
- _amsg_exit
ms.assetid: 146d4faf-d763-43a4-b264-12711196456b
ms.openlocfilehash: d00283f3222a217db8337129f66b377f7c0d494e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97211402"
---
# <a name="_amsg_exit"></a>_amsg_exit

指定したランタイム エラー メッセージを出力した後に、エラー コード 255 でアプリケーションを終了します。

## <a name="syntax"></a>構文

```cpp
void _amsg_exit ( int rterrnum );
```

### <a name="parameters"></a>パラメーター

*rterrnum*<br/>
システム定義のランタイム エラー メッセージの ID 番号。

## <a name="remarks"></a>解説

この関数は、ランタイム エラー メッセージをコンソール アプリケーションの **stderr** に出力するか、Windows アプリケーションのメッセージ ボックスにメッセージを表示します。 デバッグ モードでは、終了する前にデバッガーを起動できます。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|_amsg_exit|internal.h|
