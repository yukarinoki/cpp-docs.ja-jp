---
title: _bstr_t::GetBSTR |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _bstr_t::GetBSTR
dev_langs:
- C++
helpviewer_keywords:
- GetBSTR method [C++]
ms.assetid: 0c62ff16-4433-4183-a03c-d5a0a9b731ef
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f2c9903170f62652357264a3ea2de0839496e9e2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32409099"
---
# <a name="bstrtgetbstr"></a>_bstr_t::GetBSTR
**Microsoft 固有の仕様**  
  
 `BSTR` でラップされた `_bstr_t` の先頭を指します。  
  
## <a name="syntax"></a>構文  
  
```  
  
BSTR& GetBSTR( );  
  
```  
  
## <a name="return-value"></a>戻り値  
 `BSTR` でラップされた `_bstr_t` の先頭。  
  
## <a name="remarks"></a>コメント  
 `GetBSTR` は、`_bstr_t` を共有するすべての `BSTR` オブジェクトに影響します。 複数の `_bstr_t` がコピー コンストラクターおよび `BSTR` を使用して `operator=` を共有できます。  
  
## <a name="example"></a>例  
 参照してください[_bstr_t::assign](../cpp/bstr-t-assign.md)使用例については`GetBSTR`します。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_bstr_t クラス](../cpp/bstr-t-class.md)