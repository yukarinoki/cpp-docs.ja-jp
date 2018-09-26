---
title: _stat 構造体の st_mode フィールド定数 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- S_IFCHR
- S_IFDIR
- _S_IWRITE
- S_IFMT
- _S_IFDIR
- _S_IREAD
- S_IEXEC
- _S_IEXEC
- _S_IFMT
- S_IWRITE
- S_IFREG
- S_IREAD
- _S_IFCHR
- _S_IFREG
dev_langs:
- C++
helpviewer_keywords:
- S_IFDIR constant
- stat structure
- S_IWRITE constant
- S_IEXEC constant
- _S_IFREG constant
- S_IREAD constant
- stat structure, constants
- _S_IFMT constant
- st_mode field constants
- S_IFMT constant
- _S_IEXEC constant
- _S_IWRITE constant
- _S_IFDIR constant
- S_IFREG constant
- S_IFCHR constant
- _S_IREAD constant
- _S_IFCHR constant
ms.assetid: fd462004-7563-4766-8443-30b0a86174b6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fd7278d017002ff0d5aa716db61fdcdb54e24018
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46051139"
---
# <a name="stat-structure-stmode-field-constants"></a>_stat 構造体の st_mode フィールド定数

## <a name="syntax"></a>構文

```

#include <sys/stat.h>

```

## <a name="remarks"></a>コメント

これらの定数は、[_stat 構造体](../c-runtime-library/standard-types.md)の **st_mode** フィールドでファイルの種類を示すために使用されます。

ビット マスク定数を以下に示します。

|定数|説明|
|--------------|-------------|
|`_S_IFMT`|ファイルの種類のマスク|
|`_S_IFDIR`|ディレクトリ|
|`_S_IFCHR`|特殊な文字 (設定されている場合に、デバイスを示す)|
|`_S_IFREG`|Regular|
|`_S_IREAD`|読み取りアクセス許可、所有者|
|`_S_IWRITE`|書き込みアクセス許可、所有者|
|`_S_IEXEC`|実行/検索アクセス許可、所有者|

## <a name="see-also"></a>参照

[_stat、_wstat 関数](../c-runtime-library/reference/stat-functions.md)<br/>
[_fstat、_fstat32、_fstat64、_fstati64、_fstat32i64、_fstat64i32](../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)<br/>
[標準の型](../c-runtime-library/standard-types.md)<br/>
[グローバル定数](../c-runtime-library/global-constants.md)