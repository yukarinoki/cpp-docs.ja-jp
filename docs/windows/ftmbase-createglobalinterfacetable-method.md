---
title: Ftmbase::createglobalinterfacetable メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- ftm/Microsoft::WRL::FtmBase::CreateGlobalInterfaceTable
dev_langs:
- C++
helpviewer_keywords:
- CreateGlobalInterfaceTable method
ms.assetid: bb82a0c5-22b9-4844-9204-7922033d8b07
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6c042b6bd17da3459f499f9eb1c9167343c2e2ab
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42578774"
---
# <a name="ftmbasecreateglobalinterfacetable-method"></a>FtmBase::CreateGlobalInterfaceTable メソッド

グローバル インターフェイス テーブル (GIT) を作成します。

## <a name="syntax"></a>構文

```cpp
static HRESULT CreateGlobalInterfaceTable(
   __out IGlobalInterfaceTable **git
);
```

### <a name="parameters"></a>パラメーター

*Git*  
この操作が完了時は、グローバル インターフェイス テーブルへのポインター。

## <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。

## <a name="remarks"></a>Remarks

詳細については、次を参照してください。、`IGlobalInterfaceTable`でトピック、 **COM インターフェイス**のサブトピック、 **COM 参照**MSDN ライブラリの「します。

## <a name="requirements"></a>要件

**ヘッダー:** ftm.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[FtmBase クラス](../windows/ftmbase-class.md)