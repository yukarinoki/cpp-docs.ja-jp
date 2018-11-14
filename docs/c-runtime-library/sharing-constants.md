---
title: 共有モード定数
ms.date: 11/04/2016
f1_keywords:
- _SH_DENYNO
- _SH_DENYRD
- _SH_DENYRW
- _SH_DENYWR
- _SH_COMPAT
helpviewer_keywords:
- _SH_DENYRW constant
- SH_DENYRD constant
- _SH_COMPAT constant
- _SH_DENYRD constant
- SH_DENYRW constant
- sharing constants
- SH_DENYNO constant
- _SH_DENYWR constant
- SH_DENYWR constant
- _SH_DENYNO constant
- SH_COMPAT constant
ms.assetid: 95fadc3a-55dc-473d-98b5-e8211900465d
ms.openlocfilehash: ecc7e5fc5afaf1d6d97f3ab46be3b1ed3001d8e5
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2018
ms.locfileid: "51519543"
---
# <a name="sharing-constants"></a>共有モード定数

ファイル共有モードの定数。

## <a name="syntax"></a>構文

```

#include <share.h>
```

## <a name="remarks"></a>コメント

*shflag* 引数で、1 つまたは複数のマニフェスト定数で構成される共有モードを決定します。 これらは、*oflag* 引数と組み合わせて使用できます (「[ファイル定数](../c-runtime-library/file-constants.md)」をご覧ください)。

次の表に、定数とそれぞれの意味を示します。

|定数|説明|
|--------------|-------------|
|`_SH_DENYRW`|ファイルへの読み取りおよび書き込みアクセスを拒否|
|`_SH_DENYWR`|ファイルへの書き込みアクセスを拒否|
|`_SH_DENYRD`|ファイルへの読み取りアクセスを拒否|
|`_SH_DENYNO`|読み取りおよび書き込みアクセスを許可|
|`_SH_SECURE`|セキュリティで保護されたモードを設定 (共有読み取り、排他的な書き込みアクセス)。|

## <a name="see-also"></a>参照

[_sopen、_wsopen](../c-runtime-library/reference/sopen-wsopen.md)<br/>
[_fsopen、_wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)<br/>
[グローバル定数](../c-runtime-library/global-constants.md)