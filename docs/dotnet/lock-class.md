---
title: lock クラス
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- msclr::lock
- msclr.lock
- lock
helpviewer_keywords:
- lock class
ms.assetid: 5123edd9-6aed-497d-9a0b-f4b6d6c0d666
ms.openlocfilehash: 8876810b15a7d2736f2c8ab0ca1f4c6011918a5f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50547135"
---
# <a name="lock-class"></a>lock クラス

このクラスは、複数のスレッドからオブジェクトへのアクセスを同期するためのロックの取得を自動化します。  作成されるときにロックを取得し、リリースが破棄されるとロック。

## <a name="syntax"></a>構文

```
ref class lock;
```

## <a name="remarks"></a>Remarks

`lock` CLR オブジェクトに対してのみ使用できますが、CLR コードでのみ使用できます。

ロックのクラスは内部的には、<xref:System.Threading.Monitor>アクセスを同期します。 同期の詳細については、このトピックを参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー ファイル** \<msclr\lock.h >

**Namespace** msclr

## <a name="see-also"></a>関連項目

[lock](../dotnet/lock.md)<br/>
[lock のメンバー](../dotnet/lock-members.md)