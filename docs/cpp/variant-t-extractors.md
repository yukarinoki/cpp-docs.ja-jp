---
title: _variant_t 抽出 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _variant_t.operatordouble
- operatorlong
- _variant_t::operator_bstr_t
- operatordouble
- _variant_t.operatorCY
- operatorCY
- _variant_t::operatorCY
- _variant_t::operatordouble
- operatorfloat
- operatorBYTE
- _variant_t.operatorDECIMAL
- _variant_t::operatorlong
- operatorIDispatch
- _variant_t.operatorBYTE
- operatorDECIMAL
- _variant_t.operator_bstr_t
- _variant_t::operatorDECIMAL
- _variant_t.operatorIUnknown
- _variant_t.operatorlong
- _variant_t::operatorIDispatch
- _variant_t::operatorIUnknown
- operatorIUnknown
- _variant_t.operatorbool
- _variant_t::operatorBYTE
- _variant_t.operatorfloat
- operator_bstr_t
- _variant_t::operatorbool
- operatorshort
- _variant_t::operatorshort
- _variant_t::operatorfloat
- _variant_t.operatorIDispatch
- _variant_t.operatorshort
dev_langs:
- C++
helpviewer_keywords:
- extractors, _variant_t class
- operator CY
- operator IDispatch
- operator SHORT
- operator double
- operator long
- operator _bstr_t
- operator DECIMAL
- operator float
- operator bool
- operator BYTE
- operator IUnknown
ms.assetid: 33c1782f-045a-4673-9619-1d750efc83a9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3a8480a645728808ef4eae7a42c5080313d9fc6f
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2018
ms.locfileid: "37940346"
---
# <a name="variantt-extractors"></a>_variant_t 抽出
**Microsoft 固有の仕様**  
  
 カプセル化されたデータを抽出`VARIANT`オブジェクト。  
  
## <a name="syntax"></a>構文  
  
```  
operator short( ) const;   
operator long( ) const;   
operator float( ) const;   
operator double( ) const;   
operator CY( ) const;   
operator _bstr_t( ) const;   
operator IDispatch*( ) const;   
operator bool( ) const;   
operator IUnknown*( ) const;   
operator DECIMAL( ) const;   
operator BYTE( ) const;  
operator VARIANT() const throw();  
operator char() const;  
operator unsigned short() const;  
operator unsigned long() const;  
operator int() const;  
operator unsigned int() const;  
operator __int64() const;  
operator unsigned __int64() const;  
```  
  
## <a name="remarks"></a>Remarks  
 カプセル化されたから生データを抽出`VARIANT`します。 場合、`VARIANT`されませんが、適切な型に既に`VariantChangeType`変換を実行するために使用し、障害発生時にエラーが生成されます。  
  
-   **operator short ()** 抽出、**短い**整数値。  
  
-   **operator long ()** 抽出、**長い**整数値。  
  
-   **operator float ()** 抽出、 **float**数値を指定します。  
  
-   **operator double ()** 抽出、**二重**整数値。  
  
-   **operator CY ()** 抽出、`CY`オブジェクト。  
  
-   **operator bool ()** 抽出、 **bool**値。  
  
-   **operator DECIMAL ()** 抽出、`DECIMAL`値。  
  
-   **operator BYTE ()** 抽出、`BYTE`値。  
  
-   **operator _bstr_t ()** でカプセル化されると、文字列を抽出する`_bstr_t`オブジェクト。  
  
-   **演算子 IDispatch\*()** からカプセル化されたディスパッチ インターフェイス ポインターを抽出します`VARIANT`します。 `AddRef` 呼び出すことは、結果のポインターで呼び出される`Release`解放します。  
  
-   **演算子 IUnknown\*()** からカプセル化された COM インターフェイス ポインターを抽出します`VARIANT`します。 `AddRef` 呼び出すことは、結果のポインターで呼び出される`Release`解放します。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_variant_t クラス](../cpp/variant-t-class.md)
