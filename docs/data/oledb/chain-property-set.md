---
title: CHAIN_PROPERTY_SET |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CHAIN_PROPERTY_SET
dev_langs:
- C++
helpviewer_keywords:
- CHAIN_PROPERTY_SET macro
ms.assetid: 2bcf6d7d-f4e5-480d-9140-1e32a0994c94
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 9db57535f3f0bc7653c80b83c3e0115727eed707
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="chainpropertyset"></a>CHAIN_PROPERTY_SET
このマクロは、プロパティのグループを一緒にチェーンします。  
  
## <a name="syntax"></a>構文  
  
```cpp
CHAIN_PROPERTY_SET(ChainClass)  
  
```  
  
#### <a name="parameters"></a>パラメーター  
 *ChainClass*  
 [in]プロパティにチェーンするクラスの名前。 これは、セッション、コマンド、またはデータ ソース オブジェクト クラス) などのマップが格納されている ATL プロジェクト ウィザードで生成されるクラスです。  
  
## <a name="remarks"></a>コメント  
 独自のクラスを別のクラスからプロパティ セットのチェーンし、クラスから直接プロパティにアクセスすることができます。  
  
> [!CAUTION]
>  このマクロを慎重に使用します。 不適切に使用するには、コンシューマーの OLE DB 準拠合致テストが失敗する可能性があります。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>関連項目  
 [OLE DB プロバイダー テンプレート用マクロ](../../data/oledb/macros-for-ole-db-provider-templates.md)