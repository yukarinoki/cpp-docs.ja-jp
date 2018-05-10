---
title: CDaoIndexFieldInfo 構造体 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDaoIndexFieldInfo
dev_langs:
- C++
helpviewer_keywords:
- CDaoIndexFieldInfo structure [MFC]
- DAO (Data Access Objects), Index Fields collection
ms.assetid: 097ee8a6-83b1-4db7-8f05-d62a2deefe19
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7be9a6a9db842f1e80be62f48a9990cff36168e5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cdaoindexfieldinfo-structure"></a>CDaoIndexFieldInfo 構造体
`CDaoIndexFieldInfo`構造体には、データ アクセス オブジェクト (DAO) に対して定義されているインデックス フィールド オブジェクトに関する情報が含まれています。  
  
## <a name="syntax"></a>構文  
  
```  
struct CDaoIndexFieldInfo  
{  
    CString m_strName;          // Primary  
    BOOL m_bDescending;         // Primary  
};  
```  
  
#### <a name="parameters"></a>パラメーター  
 `m_strName`  
 インデックスのフィールド オブジェクトの一意名です。 詳細については、DAO ヘルプの「名前プロパティ」を参照してください。  
  
 *m_bDescending*  
 Index オブジェクトによって定義されているインデックスの順序を示します。 **TRUE**は降順の場合。  
  
## <a name="remarks"></a>コメント  
 Index オブジェクトには、いくつかのフィールド、テーブル定義 (またはテーブルに基づくレコード セット) がでインデックスを作成するフィールドを示すことができます。 プライマリの上記への参照で情報を返す方法を示します、`m_pFieldInfos`のメンバー、 [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md)呼び出すことによって取得したオブジェクト、`GetIndexInfo`クラスのメンバー関数[どちら](../../mfc/reference/cdaotabledef-class.md#getindexinfo)または[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md#getindexinfo)です。  
  
 オブジェクトのインデックスとインデックス フィールド オブジェクトは、MFC クラスによって表されません。 DAO オブジェクト クラスの基になる MFC オブジェクトの代わりに、[どちら](../../mfc/reference/cdaotabledef-class.md)または[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)インデックス コレクションと呼ばれるインデックス オブジェクトのコレクションを格納します。 さらに、各インデックス オブジェクトには、フィールド オブジェクトのコレクションが含まれています。 これらのクラスは、インデックス情報の各アイテムにアクセスするメンバー関数を指定するか、すべて同時にアクセスすることができます、`CDaoIndexInfo`オブジェクトを呼び出して、`GetIndexInfo`親オブジェクトのメンバー関数。 `CDaoIndexInfo`オブジェクトを持つデータ メンバー、`m_pFieldInfos`の配列を指す`CDaoIndexFieldInfo`オブジェクト。  
  
 呼び出す、`GetIndexInfo`では、インデックスがコレクションが含まれる tabledef またはレコード セット オブジェクトのメンバー関数には、興味のあるインデックス オブジェクトが格納されています。 その後アクセス、`m_pFieldInfos`のメンバー、 [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md)オブジェクト。 長さ、`m_pFieldInfos`に配列が格納されている`m_nFields`です。 `CDaoIndexFieldInfo` 定義、`Dump`デバッグでメンバー関数を作成します。 使用することができます`Dump`の内容をダンプする`CDaoIndexFieldInfo`オブジェクト。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdao.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoTableDef::GetIndexInfo](../../mfc/reference/cdaotabledef-class.md#getindexinfo)   
 [CDaoRecordset::GetIndexInfo](../../mfc/reference/cdaorecordset-class.md#getindexinfo)

