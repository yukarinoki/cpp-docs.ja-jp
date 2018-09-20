---
title: Synclockwithstatust::synclockwithstatust コンス トラクター |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::SyncLockWithStatusT
dev_langs:
- C++
helpviewer_keywords:
- SyncLockWithStatusT, constructor
ms.assetid: 5d2fb820-ae1b-495f-8084-ebb4fecc3104
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 020632ff17ade10e7fcb9cd46d245849189b6860
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46416787"
---
# <a name="synclockwithstatustsynclockwithstatust-constructor"></a>SyncLockWithStatusT::SyncLockWithStatusT コンストラクター

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

## <a name="syntax"></a>構文

```cpp
SyncLockWithStatusT(
   _Inout_ SyncLockWithStatusT&& other
);

explicit SyncLockWithStatusT(
   typename SyncTraits::Type sync,
   DWORD status
);
```

### <a name="parameters"></a>パラメーター

*other*<br/>
別の右辺値参照**SyncLockWithStatusT**オブジェクト。

*sync*<br/>
別の参照**SyncLockWithStatusT**オブジェクト。

*status*<br/>
値、 [status _](../windows/synclockwithstatust-status-data-member.md)のデータ メンバー、*他*パラメーターまたは*同期*パラメーター。

## <a name="remarks"></a>Remarks

新しいインスタンスを初期化、 **SyncLockWithStatusT**クラス。

最初のコンス トラクターは、現在**SyncLockWithStatusT**から別のオブジェクト**SyncLockWithStatusT**パラメーターで指定された*他*、し、他の無効化**SyncLockWithStatusT**オブジェクト。 2 番目のコンス トラクターは**保護**、し、現在の初期化**SyncLockWithStatusT**オブジェクトを無効な状態にします。

## <a name="requirements"></a>要件

**ヘッダー:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers::Details

## <a name="see-also"></a>関連項目

[SyncLockWithStatusT クラス](../windows/synclockwithstatust-class.md)<br/>
[SyncLockWithStatusT::GetStatus メソッド](../windows/synclockwithstatust-getstatus-method.md)