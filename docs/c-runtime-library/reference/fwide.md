---
title: fwide | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- fwide
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
- fwide
dev_langs:
- C++
helpviewer_keywords:
- fwide function
ms.assetid: a4641f5b-d74f-4946-95d5-53a64610d28d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fd52c450e2eb34c40d44d00a76550c401abcb6c9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32397269"
---
# <a name="fwide"></a>fwide

未実装。

## <a name="syntax"></a>構文

```C
int fwide(
   FILE *stream,
   int mode;
);
```

### <a name="parameters"></a>パラメーター

*ストリーム*<br/>
ポインター**ファイル**構造 (無視されます)。

*モード*<br/>
ストリームの新しい幅: ワイド文字の場合は正、バイトの場合は負、変更しない場合は 0 にします  (この値は無視されます)。

## <a name="return-value"></a>戻り値

この関数が返す現在だけ*モード*です。

## <a name="remarks"></a>コメント

この関数の現在のバージョンは、標準に準拠していません。

## <a name="requirements"></a>要件

|関数|必須ヘッダー|
|--------------|---------------------|
|**fwide**|\<wchar.h>|

詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。