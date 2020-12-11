---
description: '詳細情報: ウィンドウの特徴について'
title: ATL ウィンドウの特徴
ms.date: 11/04/2016
helpviewer_keywords:
- window traits
ms.assetid: c90cf850-9e91-49da-9cf3-ad4efb30347d
ms.openlocfilehash: a42ef66afe09e0e528f05419799dce48c43b1bbf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97157296"
---
# <a name="understanding-window-traits"></a>ウィンドウの特徴について

ウィンドウの特徴クラスは、ATL ウィンドウオブジェクトの作成に使用されるスタイルを標準化するための簡単な方法を提供します。 ウィンドウの特徴は、クラスレベルで既定のウィンドウスタイルを指定する方法として、 [CWindowImpl](../atl/reference/cwindowimpl-class.md) および他の ATL ウィンドウクラスによってテンプレートパラメーターとして受け入れられます。

ウィンドウインスタンスの作成者が [Create](../atl/reference/cwindowimpl-class.md#create)の呼び出しで明示的にスタイルを提供していない場合は、特徴クラスを使用して、ウィンドウが引き続き正しいスタイルで作成されていることを確認できます。 特定のスタイルがそのウィンドウクラスのすべてのインスタンスに対して設定されていることを確認しながら、インスタンスごとに他のスタイルを設定することもできます。

## <a name="atl-window-traits-templates"></a>ATL ウィンドウの特徴テンプレート

ATL には、コンパイル時にテンプレートパラメーターを使用して既定のスタイルを設定できる2つのウィンドウの特徴特性テンプレートが用意されています。

|クラス|説明|
|-----------|-----------------|
|[CWinTraits](../atl/reference/cwintraits-class.md)|このテンプレートは、の呼び出しで他のスタイルが指定されていない場合にのみ使用される既定のウィンドウスタイルを提供するときに使用し `Create` ます。 実行時に指定されるスタイルは、コンパイル時に設定されるスタイルよりも優先されます。|
|[CWinTraitsOR](../atl/reference/cwintraitsor-class.md)|ウィンドウクラスに常に設定する必要があるスタイルを指定する場合は、このクラスを使用します。 実行時に提供されるスタイルは、コンパイル時にビットごとの OR 演算子を使用して設定されたスタイルと組み合わされます。|

これらのテンプレートに加えて、ATL には、 `CWinTraits` 一般的に使用されるウィンドウスタイルの組み合わせ用のテンプレートの定義済みの特殊化が多数用意されています。 詳細については、 [CWinTraits](../atl/reference/cwintraits-class.md) のリファレンスドキュメントを参照してください。

## <a name="custom-window-traits"></a>カスタムウィンドウの特徴

ATL によって提供されるテンプレートの1つを特殊化するだけでは不十分で、独自の特徴クラスを作成する必要がある場合、との2つの静的関数を実装するクラスを作成する必要があります。 `GetWndStyle` `GetWndStyleEx`

[!code-cpp[NVC_ATL_Windowing#68](../atl/codesnippet/cpp/understanding-window-traits_1.h)]

これらの各関数には、実行時に、新しいスタイル値を生成するために使用できるスタイル値がいくつか渡されます。 ウィンドウの特徴クラスが ATL ウィンドウクラスのテンプレート引数として使用されている場合、これらの静的関数に渡されたスタイル値は、 [作成](../atl/reference/cwindowimpl-class.md#create)するスタイル引数として渡されたものになります。

## <a name="see-also"></a>関連項目

[ウィンドウクラス](../atl/atl-window-classes.md)
