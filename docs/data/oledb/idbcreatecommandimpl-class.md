---
title: IDBCreateCommandImpl クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::IDBCreateCommandImpl
- IDBCreateCommandImpl
- ATL.IDBCreateCommandImpl
- IDBCreateCommandImpl.CreateCommand
- CreateCommand
- IDBCreateCommandImpl::CreateCommand
dev_langs:
- C++
helpviewer_keywords:
- IDBCreateCommandImpl class
- CreateCommand method
ms.assetid: eac4755e-1668-42e1-958e-a35620c385ae
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b06d6c730562203cdef1191a9d73012c3b19c2c8
ms.sourcegitcommit: 3a141cf07b5411d5f1fdf6cf67c4ce928cf389c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/11/2018
ms.locfileid: "49083968"
---
# <a name="idbcreatecommandimpl-class"></a>IDBCreateCommandImpl クラス

実装を提供、 [IDBCreateCommand](/previous-versions/windows/desktop/ms711625)インターフェイス。  
  
## <a name="syntax"></a>構文

```cpp
template <class T, class CommandClass >  
class ATL_NO_VTABLE IDBCreateCommandImpl   
   : public IDBCreateCommand  
```  
  
### <a name="parameters"></a>パラメーター  

*T*<br/>
セッション オブジェクトから派生した`IDBCreateCommandImpl`します。  
  
*CommandClass*<br/>
コマンド クラス。  

## <a name="requirements"></a>要件  

**ヘッダー:** atldb.h  
  
## <a name="members"></a>メンバー  
  
### <a name="interface-methods"></a>インターフェイス メソッド  
  
|||  
|-|-|  
|[CreateCommand](#createcommand)|新しいコマンドを作成します。|  
  
## <a name="remarks"></a>Remarks  

新しいコマンドを取得するセッション オブジェクトの省略可能なインターフェイスです。  

## <a name="createcommand"></a> Idbcreatecommandimpl::createcommand

新しいコマンドを作成し、要求されたインターフェイスを返します。  
  
### <a name="syntax"></a>構文  
  
```cpp
STDMETHOD(CreateCommand)(IUnknown * pUnkOuter,   
   REFIID riid,   
   IUnknown ** ppvCommand);  
```  
  
#### <a name="parameters"></a>パラメーター  

参照してください[idbcreatecommand::createcommand](/previous-versions/windows/desktop/ms709772)で、 *OLE DB プログラマーズ リファレンス*します。  
  
いくつかのパラメーターに対応*OLE DB プログラマーズ リファレンス*で説明されている別の名前のパラメーター `IDBCreateCommand::CreateCommand`:  
  
|OLE DB テンプレート パラメーター|*OLE DB プログラマーズ リファレンス*パラメーター|  
|--------------------------------|------------------------------------------------|  
|*ppvCommand*|*ppCommand*|  
  
## <a name="see-also"></a>関連項目  

[OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)