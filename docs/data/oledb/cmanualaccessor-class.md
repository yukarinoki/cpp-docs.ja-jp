---
title: CManualAccessor クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CManualAccessor
- ATL.CManualAccessor
- CManualAccessor
- ATL::CManualAccessor::AddBindEntry
- ATL.CManualAccessor.AddBindEntry
- CManualAccessor::AddBindEntry
- AddBindEntry
- CManualAccessor.AddBindEntry
- CManualAccessor::AddParameterEntry
- ATL.CManualAccessor.AddParameterEntry
- CManualAccessor.AddParameterEntry
- AddParameterEntry
- ATL::CManualAccessor::AddParameterEntry
- ATL::CManualAccessor::CreateAccessor
- CreateAccessor
- ATL.CManualAccessor.CreateAccessor
- CManualAccessor.CreateAccessor
- CManualAccessor::CreateAccessor
- ATL::CManualAccessor::CreateParameterAccessor
- ATL.CManualAccessor.CreateParameterAccessor
- CManualAccessor.CreateParameterAccessor
- CreateParameterAccessor
- CManualAccessor::CreateParameterAccessor
dev_langs:
- C++
helpviewer_keywords:
- CManualAccessor class
- AddBindEntry method
- AddParameterEntry method
- CreateAccessor method
- CreateParameterAccessor method
ms.assetid: a0088074-7135-465c-b228-69097a50b8cc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f94e1100398b3f338fdc34839aee9a1e8f67871c
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2018
ms.locfileid: "39338377"
---
# <a name="cmanualaccessor-class"></a>CManualAccessor クラス
高度な使用するために設計されたアクセサーの型を表します。  
  
## <a name="syntax"></a>構文

```cpp
class CManualAccessor : public CAccessorBase  
```  

## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[AddBindEntry](#addbindentry)|出力列にバインド エントリを追加します。|  
|[AddParameterEntry](#addparameterentry)|パラメーターのアクセサーにパラメーターの入力を追加します。|  
|[CreateAccessor](#createaccessor)|列バインド構造体のメモリを割り当て、列のデータ メンバーを初期化します。|  
|[CreateParameterAccessor](#createparameteraccessor)|パラメーター バインド構造体のメモリを割り当て、パラメーターのデータ メンバーを初期化します。|  
  
## <a name="remarks"></a>Remarks  
 使用して`CManualAccessor`実行時の関数呼び出しによって出力列のバインドと、パラメーターを指定できます。  

## <a name="addbindentry"></a> Cmanualaccessor::addbindentry
出力列にバインド エントリを追加します。  
  
### <a name="syntax"></a>構文  
  
```cpp
void AddBindEntry(DBORDINAL nOrdinal,  
   DBTYPE wType,  DBLENGTH nColumnSize,  
   void* pData,  
   void* pLength = NULL,  
   void* pStatus = NULL) throw ();  
```  
  
#### <a name="parameters"></a>パラメーター  
 参照してください[DBBINDING](https://msdn.microsoft.com/library/ms716845.aspx)で、 *OLE DB プログラマーズ リファレンス*します。  
  
 *nOrdinal*  
 [in]列番号。  
  
 *wType*  
 [in]データを入力します。  
  
 *nColumnSize*  
 [in]列のサイズ (バイト単位)。  
  
 *pData*  
 [in]バッファーに格納されている列のデータへのポインター。  
  
 *pLength*  
 [in]必要な場合は、フィールドの長さへのポインター。  
  
 *pStatus*  
 [in]必要な場合は、列の状態にバインドする変数へのポインター。  
  
### <a name="remarks"></a>Remarks  
 この関数を使用するには、まず[CreateAccessor](../../data/oledb/cmanualaccessor-createaccessor.md)します。 指定された列の数よりも多くのエントリを追加することはできません`CreateAccessor`します。 
  
## <a name="addparameterentry"></a> Cmanualaccessor::addparameterentry
パラメーターのエントリの構造体には、パラメーターの入力を追加します。  
  
### <a name="syntax"></a>構文  
  
```cpp
void AddParameterEntry(DBORDINAL nOrdinal,  
   DBTYPE wType,  DBLENGTH nColumnSize,  
   void* pData,  
   void* pLength = NULL,  
   void* pStatus = NULL,  
   DBPARAMIO eParamIO = DBPARAMIO_INPUT) throw ();  
```  
  
#### <a name="parameters"></a>パラメーター  
 参照してください[DBBINDING](https://msdn.microsoft.com/library/ms716845.aspx)で、 *OLE DB プログラマーズ リファレンス*します。  
  
 *nOrdinal*  
 [in]パラメーターの数。  
  
 *wType*  
 [in]データを入力します。  
  
 *nColumnSize*  
 [in]列のサイズ (バイト単位)。  
  
 *pData*  
 [in]バッファーに格納されている列のデータへのポインター。  
  
 *pLength*  
 [in]必要な場合は、フィールドの長さへのポインター。  
  
 *pStatus*  
 [in]必要な場合は、列の状態にバインドする変数へのポインター。  
  
 *eParamIO*  
 [in]バインディングが関連付けられているパラメーターが、入力、入力/出力、または出力パラメーターであるかどうかを指定します。  
  
### <a name="remarks"></a>Remarks  
 この関数を使用するには、まず[CreateParameterAccessor](../../data/oledb/cmanualaccessor-createparameteraccessor.md)します。 

## <a name="createaccessor"></a> Cmanualaccessor::createaccessor
列バインド構造体のメモリを割り当て、列のデータ メンバーを初期化します。  
  
### <a name="syntax"></a>構文  
  
```cpp
HRESULT CreateAccessor(int nBindEntries,   
  void* pBuffer,   
   DBLENGTH nBufferSize) throw();  
```  
  
#### <a name="parameters"></a>パラメーター  
 *nBindEntries*  
 [in]列の数。 この数はへの呼び出しの数に一致する必要があります、 [cmanualaccessor::addbindentry](../../data/oledb/cmanualaccessor-addbindentry.md)関数。  
  
 *pBuffer*  
 [in]出力列が格納されているバッファーへのポインター。  
  
 *nBufferSize*  
 [in]バッファーのバイト単位のサイズ。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値の 1 つ。  
  
### <a name="remarks"></a>Remarks  
 呼び出す前に、この関数を呼び出し、`CManualAccessor::AddBindEntry`関数。  

## <a name="createparameteraccessor"></a> Cmanualaccessor::createparameteraccessor
パラメーター バインド構造体のメモリを割り当て、パラメーターのデータ メンバーを初期化します。  
  
### <a name="syntax"></a>構文  
  
```cpp
HRESULT CreateParameterAccessor(int nBindEntries,   
   void* pBuffer,   
   DBLENGTH nBufferSize) throw();  
```  
  
#### <a name="parameters"></a>パラメーター  
 *nBindEntries*  
 [in]列の数。  
  
 *pBuffer*  
 [in]入力列が格納されているバッファーへのポインター。  
  
 *nBufferSize*  
 [in]バッファーのバイト単位のサイズ。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値の 1 つ。  
  
### <a name="remarks"></a>Remarks  
 この関数を呼び出す前に呼び出す必要があります[AddParameterEntry](../../data/oledb/cmanualaccessor-addparameterentry.md)します。

## <a name="see-also"></a>関連項目  
 [DBViewer](../../visual-cpp-samples.md)   
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CAccessor クラス](../../data/oledb/caccessor-class.md)   
 [CDynamicAccessor クラス](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicParameterAccessor クラス](../../data/oledb/cdynamicparameteraccessor-class.md)