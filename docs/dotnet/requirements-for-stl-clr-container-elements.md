---
title: STL/CLR コンテナー要素の要件 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- C++ Standard Library, template class containers
- STL/CLR, containers
- containers, STL/CLR
- containers, C++ Standard Library
ms.assetid: 59ab240c-15bf-4701-a9f9-e7c56e5ab53f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 523b3e8d3f9c04a933f37032fcea670d75dafccf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="requirements-for-stlclr-container-elements"></a>STL/CLR コンテナー要素の要件
STL/CLR コンテナーに挿入されるすべての参照型が必要ですには、少なくとも、次の要素。  
  
-   パブリックのコピー コンス トラクターです。  
  
-   パブリックの代入演算子。  
  
-   パブリック デストラクターです。  
  
 さらなどの連想コンテナー[設定](../dotnet/set-stl-clr.md)と[マップ](../dotnet/map-stl-clr.md)はパブリック比較演算子が定義されている必要があります`operator<`既定です。 コンテナーに対する一部の操作は、パブリックの既定のコンス トラクターとパブリックな等価演算子を定義する必要もがあります。  
  
 参照するには、参照型、値型およびハンドルのような連想コンテナーに挿入するのには、型が必要、比較演算子など`operator<`定義します。 値の型またはハンドル型を参照するには、パブリックのコピー コンス トラクター、パブリック代入演算子、およびパブリック デストラクターの要件は存在しません。  
  
## <a name="see-also"></a>関連項目  
 [C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)