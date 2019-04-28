---
title: _amsg_exit
ms.date: 11/04/2016
apiname:
- _amsg_exit
apilocation:
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
apitype: DLLExport
f1_keywords:
- _amsg_exit
helpviewer_keywords:
- _amsg_exit
ms.assetid: 146d4faf-d763-43a4-b264-12711196456b
ms.openlocfilehash: 87cd08a6c60a1e29b8a8e15edbfdd69d338d875d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62335621"
---
# <a name="amsgexit"></a>_amsg_exit

指定したランタイム エラー メッセージを出力した後に、エラー コード 255 でアプリケーションを終了します。

## <a name="syntax"></a>構文

```cpp
void _amsg_exit ( int rterrnum );
```

### <a name="parameters"></a>パラメーター

*rterrnum*<br/>
システム定義のランタイム エラー メッセージの ID 番号。

## <a name="remarks"></a>Remarks

この関数は、ランタイム エラー メッセージをコンソール アプリケーションの **stderr** に出力するか、Windows アプリケーションのメッセージ ボックスにメッセージを表示します。 デバッグ モードでは、終了する前にデバッガーを起動できます。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|_amsg_exit|internal.h|