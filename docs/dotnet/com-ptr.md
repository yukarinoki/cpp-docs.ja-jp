---
title: com::ptr |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- ptr
dev_langs:
- C++
helpviewer_keywords:
- com::ptr
ms.assetid: ee302e3c-8fed-4875-a372-2e55003718d3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: f5e6a3f7936e21d22282fe37a29b5d91f2e50caa
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46434493"
---
# <a name="comptr"></a>com::ptr

CLR クラスのメンバーとして使用できる COM オブジェクトのラッパーです。 また、ラッパーには、そのデストラクターが呼び出されたときに、オブジェクトに所有されている参照を解放し、COM オブジェクトの有効期間管理が自動化されます。 類似しています[CComPtr クラス](../atl/reference/ccomptr-class.md)します。

## <a name="syntax"></a>構文

```
#include <msclr\com\ptr.h>
```

## <a name="remarks"></a>Remarks

[com::ptr クラス](../dotnet/com-ptr-class.md)で定義されている、 \<msclr\com\ptr.h > ファイル。

## <a name="see-also"></a>関連項目

[C++ のサポート ライブラリ](../dotnet/cpp-support-library.md)