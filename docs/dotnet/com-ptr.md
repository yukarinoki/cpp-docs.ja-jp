---
description: 詳細については、「com::p tr」を参照してください。
title: com::ptr
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- msclr/com/com::ptr
helpviewer_keywords:
- com::ptr
ms.assetid: ee302e3c-8fed-4875-a372-2e55003718d3
ms.openlocfilehash: bbfc38f10afc7d80a87e1bed0bc94716c83b75f0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97124372"
---
# <a name="comptr"></a>com::ptr

CLR クラスのメンバーとして使用できる COM オブジェクトのラッパー。 ラッパーは、COM オブジェクトの有効期間の管理も自動化します。これにより、デストラクターが呼び出されたときに、オブジェクトに対して所有されている参照が解放されます。 [CComPtr クラス](../atl/reference/ccomptr-class.md)に似ています。

## <a name="syntax"></a>構文

```
#include <msclr\com\ptr.h>
```

## <a name="remarks"></a>解説

[com::p Tr クラス](../dotnet/com-ptr-class.md) がファイルで定義されてい \<msclr\com\ptr.h> ます。

## <a name="see-also"></a>関連項目

[C++ サポートライブラリ](../dotnet/cpp-support-library.md)
