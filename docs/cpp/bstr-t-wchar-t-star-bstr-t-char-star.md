---
title: _bstr_t::wchar_t *、_bstr_t::char* |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _bstr_t::wchar_t*
- _bstr_t::char*
dev_langs:
- C++
helpviewer_keywords:
- operator wchar_t* [C++]
- operator char* [C++]
ms.assetid: acd9f4a7-b427-42c2-aaae-acae21cab317
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ebe1f3ad7b0fc46e1edba013f4cc986f1771972d
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2018
ms.locfileid: "39409147"
---
# <a name="bstrtwchart-bstrtchar"></a>_bstr_t::wchar_t *、_bstr_t::char*
**Microsoft 固有の仕様**  
  
 BSTR 文字をナロー文字配列またはワイド文字配列として返します。  
  
## <a name="syntax"></a>構文  
  
```  
operator const wchar_t*( ) const throw( );   
operator wchar_t*( ) const throw( );   
operator const char*( ) const;   
operator char*( ) const;  
```  
  
## <a name="remarks"></a>Remarks  
 これらの演算子は `BSTR` オブジェクトによってカプセル化された文字データを抽出するために使用できます。 返されたポインターに新しい値を割り当てると、元の BSTR データは変更されません。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_bstr_t クラス](../cpp/bstr-t-class.md)