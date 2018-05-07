---
title: Cutlprops::onpropertychanged |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- OnPropertyChanged
- CUtlProps.OnPropertyChanged
- CUtlProps::OnPropertyChanged
dev_langs:
- C++
helpviewer_keywords:
- OnPropertyChanged method
ms.assetid: c5924210-b685-46c4-87f8-1b81e5bd3378
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c9b52949db714206b6118000d004c6248b7d6235
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cutlpropsonpropertychanged"></a>CUtlProps::OnPropertyChanged
チェーンされたプロパティを処理するプロパティを設定した後に呼び出されます。  
  
## <a name="syntax"></a>構文  
  
```cpp
      virtual HRESULT OnPropertyChanged(ULONG /* iCurSet */,  
   DBPROP* pDBProp);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `iCurSet`  
 配列のインデックスのプロパティ セットです。1 つのプロパティ セットがある場合は 0 します。  
  
 `pDBProp`  
 プロパティ ID と新しい値、 [DBPROP](https://msdn.microsoft.com/en-us/library/ms717970.aspx)構造体。  
  
## <a name="return-value"></a>戻り値  
 標準の `HRESULT`。 既定の戻り値は`S_OK`します。  
  
## <a name="remarks"></a>コメント  
 ブックマークや値が別のプロパティの値に依存する更新プログラムなどの連鎖のプロパティを処理する場合は、この関数をオーバーライドする必要があります。  
  
## <a name="example"></a>例  
 この関数では、ユーザー ID を取得しますプロパティから、`DBPROP*`パラメーター。 今では、チェーンのプロパティに対して ID を比較することです。 プロパティが見つかった場合に`SetProperties`は他のプロパティと組み合わせて設定するプロパティを使用して呼び出されます。 この場合、いずれかを取得する場合、 `DBPROP_IRowsetLocate`、 `DBPROP_LITERALBOOKMARKS`、または`DBPROP_ORDEREDBOOKMARKS`プロパティ、いずれかの設定、`DBPROP_BOOKMARKS`プロパティです。  
  
 [!code-cpp[NVC_OLEDB_Provider#2](../../data/oledb/codesnippet/cpp/cutlprops-onpropertychanged_1.h)]  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>関連項目  
 [CUtlProps クラス](../../data/oledb/cutlprops-class.md)