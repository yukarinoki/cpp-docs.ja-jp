---
title: _com_ptr_t::GetActiveObject |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_ptr_t::GetActiveObject
dev_langs:
- C++
helpviewer_keywords:
- GetActiveObject method [C++]
ms.assetid: 2fa94853-0410-4620-91f2-136dae923f9f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ccff761cb9b738de9e2f0debc470746d1482ab56
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2018
ms.locfileid: "37940369"
---
# <a name="comptrtgetactiveobject"></a>_com_ptr_t::GetActiveObject
**Microsoft 固有の仕様**  
  
 指定したオブジェクトの既存のインスタンスにアタッチ、`CLSID`または`ProgID`します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      HRESULT GetActiveObject(  
   const CLSID& rclsid   
) throw( );  
HRESULT GetActiveObject(  
   LPCWSTR clsidString   
) throw( );  
HRESULT GetActiveObject(  
   LPCSTR clsidStringA   
) throw( );  
```  
  
#### <a name="parameters"></a>パラメーター  
 *rclsid*  
 `CLSID`のオブジェクト。  
  
 *clsidString*  
 保持する Unicode 文字列、 `CLSID` (以降では"**{**") または`ProgID`します。  
  
 *clsidStringA*  
 いずれかを保持する ANSI コード ページを使用し、マルチバイト文字列を`CLSID`(以降では"**{**") または`ProgID`します。  
  
## <a name="remarks"></a>Remarks  
 これらのメンバー関数は、`GetActiveObject` を呼び出して、OLE に登録されている実行中のオブジェクトへのポインターを取得し、このスマート ポインターのインターフェイス型を照会します。 結果のポインターは、この `_com_ptr_t` オブジェクトの中にカプセル化されます。 `Release` 以前にカプセル化されたポインターの参照カウントをデクリメントすると呼びます。 このルーチンは、成功または失敗を示す HRESULT を返します。  
  
-   **GetActiveObject (**`rclsid`**)** 指定したオブジェクトの既存のインスタンスにアタッチ、`CLSID`します。      
  
-   **GetActiveObject (**`clsidString`**)** 保持する Unicode 文字列を指定したオブジェクトの既存のインスタンスにアタッチ、 `CLSID` (以降では"**{**") または、 `ProgID`.      
  
-   **GetActiveObject (**`clsidStringA`**)** 保持するマルチバイト文字の文字列を指定したオブジェクトの既存のインスタンスにアタッチ、 `CLSID` (以降では"**{**") または`ProgID`.     呼び出し[MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072)、OEM コード ページではなく、ANSI コード ページで、文字列が想定しています。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_com_ptr_t クラス](../cpp/com-ptr-t-class.md)