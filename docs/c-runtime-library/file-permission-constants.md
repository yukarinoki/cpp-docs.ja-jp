---
description: 詳細については、「ファイルアクセス許可定数」を参照してください。
title: ファイルのアクセス許可定数
ms.date: 11/04/2016
helpviewer_keywords:
- S_IWRITE constant
- constants [C++], file attributes
- S_IREAD constant
- file permissions [C++]
- _S_IWRITE constant
- _S_IREAD constant
ms.assetid: 593cad33-31d1-44d2-8941-8af7d210c88c
ms.openlocfilehash: a220ec404202b1f962a4c0bf51d20b7eea2720ee
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331083"
---
# <a name="file-permission-constants"></a>ファイルのアクセス許可定数

## <a name="syntax"></a>構文

```
#include <sys/stat.h>
```

## <a name="remarks"></a>解説

`_O_CREAT` (`_open`, `_sopen`) が指定されるとき、これらの定数のいずれかが必須になります。

`pmode` 引数は、次のようにファイルのアクセス許可設定を指定します。

|定数|説明|
|--------------|-------------|
|`_S_IREAD`|読み取りが許可されます|
|`_S_IWRITE`|書き込みが許可されます|
|`_S_IREAD` &#124; `_S_IWRITE`|読み取りと書き込みが許可されます|

`_umask` の `pmode` 引数として使用されるとき、マニフェスト定数はアクセス許可を次のように設定します。

|定数|説明|
|--------------|-------------|
|`_S_IREAD`|書き込み禁止 (ファイルは読み取り専用)|
|`_S_IWRITE`|読み取り禁止 (ファイルは書き込み専用)|
|`_S_IREAD` &#124; `_S_IWRITE`|読み取りも書き込みも禁止|

## <a name="see-also"></a>関連項目

[_open、_wopen](../c-runtime-library/reference/open-wopen.md)<br/>
[_sopen、_wsopen](../c-runtime-library/reference/sopen-wsopen.md)<br/>
[_umask](../c-runtime-library/reference/umask.md)<br/>
[標準型](../c-runtime-library/standard-types.md)<br/>
[グローバル定数](../c-runtime-library/global-constants.md)
