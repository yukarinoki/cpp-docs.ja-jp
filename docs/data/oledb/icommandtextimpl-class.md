---
title: ICommandTextImpl クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ICommandText
dev_langs:
- C++
helpviewer_keywords:
- ICommandText class
ms.assetid: 9c2715cc-1e55-4468-8327-85341617ed46
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f49326dba4868ad490dc1a7122eed68271bdfa15
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33100201"
---
# <a name="icommandtextimpl-class"></a>ICommandTextImpl クラス
実装を提供、 [ICommandText](https://msdn.microsoft.com/en-us/library/ms714914.aspx)インターフェイスです。  
  
## <a name="syntax"></a>構文

```cpp
template <class T >  
class ATL_NO_VTABLE ICommandTextImpl   
   : public ICommandImpl<T, ICommandText>  
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 コマンド クラスから派生する**ICommandTextImpl**です。  
  
## <a name="members"></a>メンバー  
  
### <a name="interface-methods"></a>インターフェイス メソッド  
  
|||  
|-|-|  
|[GetCommandText](../../data/oledb/icommandtextimpl-getcommandtext.md)|テキスト コマンドの最後の呼び出しでセットを返します[SetCommandText](../../data/oledb/icommandtextimpl-setcommandtext.md)です。|  
|[SetCommandText](../../data/oledb/icommandtextimpl-setcommandtext.md)|コマンド テキストは、既存のコマンド テキストの置換を設定します。|  
  
### <a name="data-members"></a>データ メンバー  
  
|||  
|-|-|  
|[m_strCommandText](../../data/oledb/icommandtextimpl-m-strcommandtext.md)|コマンド テキストを格納します。|  
  
## <a name="remarks"></a>コメント  
 コマンドの必須のインターフェイスです。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** altdb.h  
  
## <a name="see-also"></a>関連項目  
 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)