---
title: lock クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- msclr::lock
- msclr.lock
- lock
dev_langs:
- C++
helpviewer_keywords:
- lock class
ms.assetid: 5123edd9-6aed-497d-9a0b-f4b6d6c0d666
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 7ef0887ca3eec7510717aab21ba4c6c7aba98d25
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46380296"
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

## <a name="requirements"></a>要件

**ヘッダー ファイル** \<msclr\lock.h >

**Namespace** msclr

## <a name="see-also"></a>関連項目

[lock](../dotnet/lock.md)<br/>
[lock のメンバー](../dotnet/lock-members.md)