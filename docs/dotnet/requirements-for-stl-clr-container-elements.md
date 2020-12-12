---
description: '詳細情報: STL/CLR コンテナー要素の要件'
title: STL/CLR コンテナー要素の要件
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- C++ Standard Library, template class containers
- STL/CLR, containers
- containers, STL/CLR
- containers, C++ Standard Library
ms.assetid: 59ab240c-15bf-4701-a9f9-e7c56e5ab53f
ms.openlocfilehash: 3696d9df40f69b1dd39205a2dc7a3b802e815841
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97305508"
---
# <a name="requirements-for-stlclr-container-elements"></a>STL/CLR コンテナー要素の要件

STL/CLR コンテナーに挿入されるすべての参照型には、少なくとも次の要素が必要です。

- パブリックコピーコンストラクター。

- パブリック代入演算子。

- パブリックデストラクター。

さらに、 [set](../dotnet/set-stl-clr.md) や [map](../dotnet/map-stl-clr.md) などの連想コンテナーには、既定で定義されている、パブリックな比較演算子が定義されている必要があり `operator<` ます。 コンテナーに対する一部の操作では、パブリックの既定のコンストラクターとパブリック等価演算子を定義する必要がある場合もあります。

参照型と同様に、連想コンテナーに挿入される型を参照するための値型とハンドルには、定義されたなどの比較演算子が必要 `operator<` です。 パブリックコピーコンストラクター、パブリック代入演算子、およびパブリックデストラクターの要件は、値型または参照型へのハンドルには存在しません。

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリリファレンス](../standard-library/cpp-standard-library-reference.md)
