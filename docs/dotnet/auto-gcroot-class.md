---
title: auto_gcroot クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- msclr::auto_gcroot
- msclr.auto_gcroot
- auto_gcroot
dev_langs:
- C++
helpviewer_keywords:
- auto_gcroot
ms.assetid: b5790912-265d-463e-a486-47302e91042a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: b6afad3450aff2a9243b3e4a480a374fbcd14fc7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33103867"
---
# <a name="autogcroot-class"></a>auto_gcroot クラス
自動リソース管理 (と同様に[auto_ptr クラス](../standard-library/auto-ptr-class.md)) をネイティブ型に仮想のハンドルを埋め込むには使用できます。  
  
## <a name="syntax"></a>構文  
  
```  
template<typename _element_type>  
class auto_gcroot;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `_element_type`  
 埋め込まれるマネージ型です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー ファイル** \<msclr\auto_gcroot.h >  
  
 **Namespace** msclr  
  
## <a name="see-also"></a>関連項目  
 [auto_gcroot](../dotnet/auto-gcroot.md)   
 [auto_gcroot メンバー](../dotnet/auto-gcroot-members.md)   
 [方法: ネイティブ型のハンドルを宣言します。](../dotnet/how-to-declare-handles-in-native-types.md)   
 [auto_handle クラス](../dotnet/auto-handle-class.md)