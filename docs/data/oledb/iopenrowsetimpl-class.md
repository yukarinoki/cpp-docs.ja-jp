---
title: IOpenRowsetImpl クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IOpenRowsetImpl
dev_langs:
- C++
helpviewer_keywords:
- IOpenRowsetImpl class
ms.assetid: d259cedc-1db4-41cf-bc9f-5030907ab486
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: dd34987fcff3bee663a06276e3ded3c44d7ae77c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="iopenrowsetimpl-class"></a>IOpenRowsetImpl クラス
実装を提供、`IOpenRowset`インターフェイスです。  
  
## <a name="syntax"></a>構文

```cpp
template <class SessionClass>  
class IOpenRowsetImpl : public IOpenRowset  
```  
  
#### <a name="parameters"></a>パラメーター  
 `SessionClass`  
 派生したクラス、`IOpenRowsetImpl`です。  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[CreateRowset](../../data/oledb/iopenrowsetimpl-createrowset.md)|行セット オブジェクトを作成します。 ユーザーが直接呼び出されません。|  
|[OpenRowset](../../data/oledb/iopenrowsetimpl-openrowset.md)|開き、単一のベース テーブルまたはインデックスからすべての行を含む行セットを返します。 (にない ATLDB です。H)|  
  
## <a name="remarks"></a>コメント  
 [IOpenRowset](https://msdn.microsoft.com/en-us/library/ms716946.aspx)セッション オブジェクトの必須インターフェイスです。 それが開き、単一のベース テーブルまたはインデックスからすべての行を含む行セットを返します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>関連項目  
 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)