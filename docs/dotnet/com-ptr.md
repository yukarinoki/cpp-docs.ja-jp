---
title: com::ptr
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- msclr/com/com::ptr
helpviewer_keywords:
- com::ptr
ms.assetid: ee302e3c-8fed-4875-a372-2e55003718d3
ms.openlocfilehash: 993511142b72bd769fe8582b2650e5d020bd6ce2
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79545859"
---
# <a name="comptr"></a>com::ptr

CLR クラスのメンバーとして使用できる COM オブジェクトのラッパー。 ラッパーは、COM オブジェクトの有効期間の管理も自動化します。これにより、デストラクターが呼び出されたときに、オブジェクトに対して所有されている参照が解放されます。 [CComPtr クラス](../atl/reference/ccomptr-class.md)に似ています。

## <a name="syntax"></a>構文

```
#include <msclr\com\ptr.h>
```

## <a name="remarks"></a>コメント

[com::p Tr クラス](../dotnet/com-ptr-class.md)は \<msclr\com\ptr.h > ファイルで定義されています。

## <a name="see-also"></a>参照

[C++ のサポート ライブラリ](../dotnet/cpp-support-library.md)
