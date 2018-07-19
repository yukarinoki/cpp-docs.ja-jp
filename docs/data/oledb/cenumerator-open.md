---
title: Cenumerator::open |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.CEnumerator.Open
- CEnumerator::Open
- ATL::CEnumerator::Open
- CEnumerator.Open
dev_langs:
- C++
helpviewer_keywords:
- Open method
ms.assetid: b22821a0-257a-4543-ad0c-2649d4ac092e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 04e6884b27f45ee86085c1b820376ed087ae68c5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33096926"
---
# <a name="cenumeratoropen"></a>CEnumerator::Open
モニカーを指定すると、いずれかの場合は、列挙子を呼び出すことによって、行セットを取得、列挙子のバインド[isourcesrowset:](https://msdn.microsoft.com/en-us/library/ms711200.aspx)です。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT Open(LPMONIKER pMoniker) throw();  


HRESULT Open(const CLSID* pClsid = & CLSID_OLEDB_ENUMERATOR) throw();  


HRESULT Open(const CEnumerator& enumerator) throw();  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pMoniker`  
 [in]列挙子のモニカーへのポインター。  
  
 *pClsid*  
 [in]ポインター、 **CLSID**の列挙子。  
  
 `enumerator`  
 [in]列挙子への参照。  
  
## <a name="return-value"></a>戻り値  
 標準の `HRESULT`。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [CEnumerator クラス](../../data/oledb/cenumerator-class.md)