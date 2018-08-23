---
title: Criticalsection::criticalsection コンス トラクター |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::CriticalSection
dev_langs:
- C++
helpviewer_keywords:
- CriticalSection, constructor
ms.assetid: 930b89be-4d74-46bd-8879-5dd4d15bcbd0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 892a32c6ff6f8e9a3a30452d05dd6e15c38a4fa8
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42605053"
---
# <a name="criticalsectioncriticalsection-constructor"></a>CriticalSection::CriticalSection コンストラクター

ミュー テックス オブジェクトに似ていますが、1 つのプロセスのスレッドのみで使用できる同期オブジェクトを初期化します。

## <a name="syntax"></a>構文

```cpp
explicit CriticalSection(
   ULONG spincount = 0
);
```

### <a name="parameters"></a>パラメーター

*spincount*  
クリティカル セクション オブジェクトのスピン カウントします。 既定値は 0 です。

## <a name="remarks"></a>Remarks

クリティカル セクションと spincounts の詳細については、次を参照してください。、`InitializeCriticalSectionAndSpinCount`で機能、**同期**Windows API のドキュメントのセクション。

## <a name="requirements"></a>要件

**ヘッダー:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>関連項目

[CriticalSection クラス](../windows/criticalsection-class.md)