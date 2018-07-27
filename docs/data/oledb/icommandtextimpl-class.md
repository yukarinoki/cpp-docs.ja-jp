---
title: ICommandTextImpl クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ICommandText
- GetCommandText
- ICommandTextImpl.GetCommandText
- ICommandTextImpl::GetCommandText
- ATL::ICommandTextImpl::m_strCommandText
- ICommandTextImpl<T>::m_strCommandText
- m_strCommandText
- ICommandTextImpl.m_strCommandText
- ICommandTextImpl::m_strCommandText
- ATL::ICommandTextImpl<T>::m_strCommandText
- ATL.ICommandTextImpl.m_strCommandText
- ICommandTextImpl.SetCommandText
- ICommandTextImpl::SetCommandText
- SetCommandText
dev_langs:
- C++
helpviewer_keywords:
- ICommandText class
- GetCommandText method
- m_strCommandText
- SetCommandText method
ms.assetid: 9c2715cc-1e55-4468-8327-85341617ed46
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2223958f2f5dbacb7c86bf2735c1de3a85d9d488
ms.sourcegitcommit: b0d6777cf4b580d093eaf6104d80a888706e7578
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/26/2018
ms.locfileid: "39269492"
---
# <a name="icommandtextimpl-class"></a>ICommandTextImpl クラス
実装を提供、 [ICommandText](https://msdn.microsoft.com/library/ms714914.aspx)インターフェイス。  
  
## <a name="syntax"></a>構文

```cpp
template <class T >  
class ATL_NO_VTABLE ICommandTextImpl   
   : public ICommandImpl<T, ICommandText>  
```  
  
### <a name="parameters"></a>パラメーター  
 *T*  
 コマンド クラスから派生した**ICommandTextImpl**します。 

## <a name="requirements"></a>必要条件  
 **ヘッダー:** altdb.h  
  
## <a name="members"></a>メンバー  
  
### <a name="interface-methods"></a>インターフェイス メソッド  
  
|||  
|-|-|  
|[GetCommandText](#getcommandtext)|テキスト コマンドの最後の呼び出しでセットを返します[SetCommandText](../../data/oledb/icommandtextimpl-setcommandtext.md)します。|  
|[SetCommandText](#setcommandtext)|既存のコマンド テキストを置き換えて、コマンド テキストを設定します。|  
  
### <a name="data-members"></a>データ メンバー  
  
|||  
|-|-|  
|[m_strCommandText](#strcommandtext)|コマンド テキストを格納します。|  
  
## <a name="remarks"></a>Remarks  
 コマンドの必須インターフェイス。  
 
## <a name="getcommandtext"></a> Icommandtextimpl::getcommandtext
テキスト コマンドの最後の呼び出しでセットを返します[SetCommandText](../../data/oledb/icommandtextimpl-setcommandtext.md)します。  
  
### <a name="syntax"></a>構文  
  
```cpp
      STDMETHOD(GetCommandText)(GUID * pguidDialect,   
   LPOLESTR * ppwszCommand);  
```  
  
#### <a name="parameters"></a>パラメーター  
 参照してください[ICommandText::GetCommandText](https://msdn.microsoft.com/library/ms709825.aspx)で、 *OLE DB プログラマーズ リファレンス*します。 *既定で*パラメーターは既定では無視されます。  

## <a name="setcommandtext"></a> Icommandtextimpl::setcommandtext
既存のコマンド テキストを置き換えて、コマンド テキストを設定します。  
  
### <a name="syntax"></a>構文  
  
```cpp
      STDMETHOD(SetCommandText)(REFGUID rguidDialect,   
   LPCOLESTR pwszCommand);  
```  
  
#### <a name="parameters"></a>パラメーター  
 参照してください[icommandtext::setcommandtext](https://msdn.microsoft.com/library/ms709757.aspx)で、 *OLE DB プログラマーズ リファレンス*します。 

## <a name="strcommandtext"></a> Icommandtextimpl::m_strcommandtext
コマンド テキストの文字列を格納します。  
  
### <a name="syntax"></a>構文  
  
```cpp
CComBSTR m_strCommandText;  
  
```  
  
## <a name="see-also"></a>関連項目  
 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)
