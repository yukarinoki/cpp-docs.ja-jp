---
title: ファイルのアクセス許可定数
ms.date: 11/04/2016
f1_keywords:
- _S_IWRITE
- _S_IREAD
helpviewer_keywords:
- S_IWRITE constant
- constants [C++], file attributes
- S_IREAD constant
- file permissions [C++]
- _S_IWRITE constant
- _S_IREAD constant
ms.assetid: 593cad33-31d1-44d2-8941-8af7d210c88c
ms.openlocfilehash: 7b9d99f8b0fc7daf8f7dc58db999c7f885a3dc8d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50648605"
---
# <a name="file-permission-constants"></a>ファイルのアクセス許可定数

## <a name="syntax"></a>構文

```

#include <sys/stat.h>

```

## <a name="remarks"></a>コメント

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

## <a name="see-also"></a>参照

[_open、_wopen](../c-runtime-library/reference/open-wopen.md)<br/>
[_sopen、_wsopen](../c-runtime-library/reference/sopen-wsopen.md)<br/>
[_umask](../c-runtime-library/reference/umask.md)<br/>
[標準の型](../c-runtime-library/standard-types.md)<br/>
[グローバル定数](../c-runtime-library/global-constants.md)