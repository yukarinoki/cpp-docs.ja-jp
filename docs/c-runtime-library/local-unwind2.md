---
title: _local_unwind2 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- _local_unwind2
apilocation:
- msvcr110_clr0400.dll
- msvcrt.dll
- msvcr100.dll
- msvcr110.dll
- msvcr80.dll
- msvcr90.dll
- msvcr120.dll
apitype: DLLExport
f1_keywords:
- _local_unwind2
- local_unwind2
dev_langs:
- C++
helpviewer_keywords:
- _local_unwind2 function
- local_unwind2 function
ms.assetid: 44f1fa82-e01e-490f-a6e6-18fc6811c28c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 47227d4be0ad1c5145a9064d11b4ea633c7d7fc1
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46035787"
---
# <a name="localunwind2"></a>_local_unwind2

内部 CRT 関数。 指定されたスコープ テーブルに示されているすべての終了ハンドラーを実行します。

## <a name="syntax"></a>構文

```
void _local_unwind2(
   PEXCEPTION_REGISTRATION xr,
   int stop
);
```

#### <a name="parameters"></a>パラメーター

*xr*<br/>
[in] 1 つのスコープ テーブルに関連付けられている登録レコード。

*stop*<br/>
[in] `_local_unwind2` の停止箇所を示す構文レベル。

## <a name="remarks"></a>コメント

このメソッドは、ランタイム環境によってのみ使用されます。 このメソッドをコードで呼び出さないでください。

このメソッドが終了ハンドラーを実行する場合、現在の構文レベルで開始し、`stop` で示されたレベルに到達するまで構文レベル内を上へ移動します。 `stop` で示されたレベルでは終了ハンドラーを実行しません。

## <a name="see-also"></a>参照

[関数リファレンス (アルファベット順)](../c-runtime-library/reference/crt-alphabetical-function-reference.md)