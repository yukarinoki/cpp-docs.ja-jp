---
title: _com_error::_com_error |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::_com_error
dev_langs:
- C++
helpviewer_keywords:
- _com_error method [C++]
ms.assetid: 0a69e46c-caab-49ef-b091-eee401253ce6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ec16faa9881fc1c69dca5f8f39b8797cf0fcff0d
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2018
ms.locfileid: "37943510"
---
# <a name="comerrorcomerror"></a>_com_error::_com_error
**Microsoft 固有の仕様**  
  
 `_com_error` オブジェクトを構築します。  
  
## <a name="syntax"></a>構文  
  
```  
  
_com_error(  
   HRESULT hr,  
   IErrorInfo* perrinfo = NULL,  
   bool fAddRef=false) throw( );  

_com_error( const _com_error& that ) throw( );  
```  
  
#### <a name="parameters"></a>パラメーター  
 *hr*  
 HRESULT 情報。  
  
 *perrinfo*  
 `IErrorInfo` オブジェクト。  
  
 `bool fAddRef=false`  
 コンス トラクターに null 以外の AddRef を呼び出すと、`IErrorInfo`インターフェイス。 こうすることで、次の例のように、インターフェイスの所有権が `_com_error` オブジェクトに渡される一般的なケースで参照カウントが正しく実行されます。  
  
```cpp 
throw _com_error(hr, perrinfo);  
```  
  
 コード所有権の転送をしないかどうか、`_com_error`オブジェクト、および`AddRef`をオフセットするために必要な`Release`で、`_com_error`デストラクターでは、次のように、オブジェクトを作成します。  
  
```cpp 
_com_error err(hr, perrinfo, true);  
```  
  
 *それ*  
 既存の `_com_error` オブジェクト。  
  
## <a name="remarks"></a>Remarks  
 最初のコンス トラクターは、HRESULT と省略可能な指定された新しいオブジェクトを作成します。`IErrorInfo`オブジェクト。 2 つ目のコンストラクターは、既存の `_com_error` オブジェクトのコピーを作成します。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_com_error クラス](../cpp/com-error-class.md)