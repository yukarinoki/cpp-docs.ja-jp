---
title: uuid (C++) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- uuid_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++], uuid
- uuid __declspec keyword
ms.assetid: 9d004621-09bc-4a8d-871b-648f5d5102d7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 93ae3ac7f0d6fff700e1c89aad197d5f03734cf5
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/02/2018
ms.locfileid: "39467109"
---
# <a name="uuid-c"></a>uuid (C++)
**Microsoft 固有の仕様**  
  
 コンパイラはクラスまたは構造体宣言または定義されている (完全な COM オブジェクトの定義のみ) 使用する GUID をアタッチします、 **uuid**属性。  
  
## <a name="syntax"></a>構文  
  
```  
__declspec( uuid("ComObjectGUID") ) declarator  
```  
  
## <a name="remarks"></a>Remarks  
 **Uuid**属性は、引数として文字列を受け取ります。 この文字列は、標準レジストリ形式の有無の GUID を名前、 **{}** 区切り記号。 例えば:  
  
```cpp 
struct __declspec(uuid("00000000-0000-0000-c000-000000000046")) IUnknown;  
struct __declspec(uuid("{00020400-0000-0000-c000-000000000046}")) IDispatch;  
```  
  
 この属性は、再宣言で適用できます。 これにより、システム ヘッダーなどのインターフェイスの定義の指定を`IUnknown`、およびその他のいくつかのヘッダーで再宣言 (など\<comdef.h >) GUID を提供します。  
  
 キーワード[_ _uuidof](../cpp/uuidof-operator.md) GUID は、ユーザー定義型にアタッチされている定数の取得に適用できます。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [__declspec](../cpp/declspec.md)   
 [キーワード](../cpp/keywords-cpp.md)