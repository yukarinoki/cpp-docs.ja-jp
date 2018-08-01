---
title: _bstr_t::copy |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _bstr_t::copy
dev_langs:
- C++
helpviewer_keywords:
- Copy method [C++]
- BSTR object [C++], copy
ms.assetid: 00ba7311-e82e-4a79-8106-5329fa2f869a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5b7032d9344ec9375059d5584d080854ffe5c775
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2018
ms.locfileid: "39405341"
---
# <a name="bstrtcopy"></a>_bstr_t::copy
**Microsoft 固有の仕様**  
  
 カプセル化された `BSTR` のコピーを生成します。  
  
## <a name="syntax"></a>構文  
  
```  
BSTR copy( bool fCopy = true ) const;  
```  
  
#### <a name="parameters"></a>パラメーター  
 *fCopy*  
 TRUE の場合、**コピー**格納されているのコピーを返します`BSTR`それ以外の場合、**コピー**実際の BSTR を返します。  
  
## <a name="remarks"></a>Remarks  
 カプセル化された `BSTR` オブジェクトの新しく割り当てられたコピーを返します。  
  
## <a name="example"></a>例  
  
```cpp 
STDMETHODIMP CAlertMsg::get_ConnectionStr(BSTR *pVal){ //  m_bsConStr is _bstr_t  
   *pVal = m_bsConStr.copy();  
}  
```  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_bstr_t クラス](../cpp/bstr-t-class.md)