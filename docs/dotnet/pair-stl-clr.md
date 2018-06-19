---
title: ペア (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::pair
dev_langs:
- C++
helpviewer_keywords:
- pair class [STL/CLR]
ms.assetid: 3326b4d9-a52a-49e5-8103-9aa5e8b352de
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 2d05dceaa763f8d0e33ccc86e783f66447c48b76
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33160824"
---
# <a name="pair-stlclr"></a>pair (STL/CLR)
このテンプレート クラスでは、値のペアをラップするオブジェクトについて説明します。  
  
## <a name="syntax"></a>構文  
  
```  
template<typename Value1,  
    typename Value2>  
    ref class pair;  
```  
  
#### <a name="parameters"></a>パラメーター  
 Value1  
 ラップされた最初の値の型。  
  
 Value2  
 2 番目のラップされた値の型。  
  
## <a name="members"></a>メンバー  
  
|型定義|説明|  
|---------------------|-----------------|  
|[pair::first_type (STL/CLR)](../dotnet/pair-first-type-stl-clr.md)|最初のラップされた値の型。|  
|[pair::second_type (STL/CLR)](../dotnet/pair-second-type-stl-clr.md)|2 番目のラップされた値の型。|  
  
|メンバー オブジェクト|説明|  
|-------------------|-----------------|  
|[pair::first (STL/CLR)](../dotnet/pair-first-stl-clr.md)|最初に格納されている値。|  
|[pair::second (STL/CLR)](../dotnet/pair-second-stl-clr.md)|2 つ目は、値を格納します。|  
  
|メンバー関数|説明|  
|---------------------|-----------------|  
|[pair::pair (STL/CLR)](../dotnet/pair-pair-stl-clr.md)|組オブジェクトを構築します。|  
|[pair::swap (STL/CLR)](../dotnet/pair-swap-stl-clr.md)|2 つのペアのコンテンツを交換します。|  
  
|演算子|説明|  
|--------------|-----------------|  
|[pair::operator= (STL/CLR)](../dotnet/pair-operator-assign-stl-clr.md)|ストアド値のペアを置き換えます。|  
  
## <a name="remarks"></a>コメント  
 オブジェクトは、値のペアを格納します。 このテンプレート クラスを使用して、2 つの値を 1 つのオブジェクトに結合します。 なお`cliext::pair`(ここで説明) ストアのみマネージ型以外の型を使用してアンマネージのペアを格納する`std::pair`で宣言された`<utility>`です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext ユーティリティ/>  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [make_pair (STL/CLR)](../dotnet/make-pair-stl-clr.md)