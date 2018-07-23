---
title: CAccessorRowset クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CAccessorRowset
- ATL.CAccessorRowset
- ATL::CAccessorRowset
- CAccessorRowset.Bind
- CAccessorRowset::Bind
- CAccessorRowset::CAccessorRowset
- CAccessorRowset.CAccessorRowset
- CAccessorRowset
- ATL.CAccessorRowset.CAccessorRowset
- ATL::CAccessorRowset::CAccessorRowset
- CAccessorRowset.Close
- CAccessorRowset::Close
- CAccessorRowset::FreeRecordMemory
- CAccessorRowset.FreeRecordMemory
- FreeRecordMemory
- GetColumnInfo
- CAccessorRowset.GetColumnInfo
- CAccessorRowset::GetColumnInfo
dev_langs:
- C++
helpviewer_keywords:
- CAccessorRowset class
- CAccessorRowset class, methods
- CAccessorRowset class, members
- Bind method
- CAccessorRowset class, constructor
- Close method
- FreeRecordMemory method
- GetColumnInfo method
ms.assetid: bd4f58ed-cebf-4d43-8985-1e5fcbf06953
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a9f869a901885b064ef4ddbbfddc23b246455a39
ms.sourcegitcommit: 04d327940787df1297b72d534f388a035d472af0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2018
ms.locfileid: "39181186"
---
# <a name="caccessorrowset-class"></a>CAccessorRowset クラス
行セットと 1 つのクラスに関連付けられているそのアクセサーをカプセル化します。  
  
## <a name="syntax"></a>構文

```cpp
template <class TAccessor = CNoAccessor, 
          template <typename T> class TRowset = CRowset>  
class CAccessorRowset : public TAccessor, public TRowset<TAccessor>  
```  
  
### <a name="parameters"></a>パラメーター  
 *TAccessor*  
 アクセサー クラス。  
  
 *TRowset*  
 行セット クラスです。  

## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[バインド](#bind)|バインドを作成します (際に使用される`bBind`として指定されて**false**で[ccommand::open](../../data/oledb/ccommand-open.md))。|  
|[CAccessorRowset](#caccessorrowset)|コンストラクターです。|  
|[閉じる](#close)|行セットとすべてのアクセサーを閉じます。|  
|[FreeRecordMemory](#freerecordmemory)|解放する必要がある現在のレコード内の列を解放します。|  
|[GetColumnInfo](#getcolumninfo)|実装[icolumnsinfo::getcolumninfo](https://msdn.microsoft.com/en-us/library/ms722704.aspx)します。|  
  
## <a name="remarks"></a>Remarks  
 クラス`TAccessor`アクセサーを管理します。 クラス*TRowset*行セットを管理します。  

## <a name="bind"></a> Caccessorrowset::bind
指定した場合は、バインドを作成します。`bBind`として**false**で[ccommand::open](../../data/oledb/ccommand-open.md)します。  
  
### <a name="syntax"></a>構文  
  
```cpp
HRESULT Bind();  
  
```  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT です。  

## <a name="caccessorrowset"></a> Caccessorrowset::caccessorrowset
`CAccessorRowset` オブジェクトを初期化します。  
  
### <a name="syntax"></a>構文  
  
```cpp
CAccessorRowset();  
  
```  

## <a name="close"></a> Caccessorrowset::close
アクティブなアクセサーと行セットを解放します。  
  
### <a name="syntax"></a>構文  
  
```cpp
void Close();  
  
```  
  
### <a name="remarks"></a>Remarks  
 関連付けられているメモリを解放します。  

## <a name="freerecordmemory"></a> Caccessorrowset::freerecordmemory
解放する必要がある現在のレコード内の列を解放します。  
  
### <a name="syntax"></a>構文  
  
```cpp
void FreeRecordMemory();  
  
```  

## <a name="getcolumninfo"></a> Caccessorrowset::getcolumninfo
開かれた行セットから列情報を取得します。  
  
### <a name="syntax"></a>構文  
  
```cpp
HRESULT GetColumnInfo(DBORDINAL* pulColumns,  
   DBCOLUMNINFO** ppColumnInfo,  
   LPOLESTR* ppStrings) const;  

HRESULT GetColumnInfo(DBORDINAL* pColumns,  
   DBCOLUMNINFO** ppColumnInfo);  
```  
  
#### <a name="parameters"></a>パラメーター  
 参照してください[icolumnsinfo::getcolumninfo](https://msdn.microsoft.com/en-us/library/ms722704.aspx)で、 *OLE DB プログラマーズ リファレンス*します。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT です。  
  
### <a name="remarks"></a>Remarks  
 ユーザーは、返される列情報と文字列バッファーを解放する必要があります。 使用する場合は、このメソッドの 2 番目のバージョンを使用して[CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)バインディングをオーバーライドする必要があります。  
  
 詳細については、次を参照してください。 [icolumnsinfo::getcolumninfo](https://msdn.microsoft.com/en-us/library/ms722704.aspx)で、 *OLE DB プログラマーズ リファレンス*します。  
  
## <a name="see-also"></a>関連項目  
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)