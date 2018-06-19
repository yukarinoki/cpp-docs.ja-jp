---
title: ATL ウィンドウ特徴 (traits) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- window traits
ms.assetid: c90cf850-9e91-49da-9cf3-ad4efb30347d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 71fbf5b3c4c3f1aa95070cbc0d30beb9e1321348
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32362369"
---
# <a name="understanding-window-traits"></a>ウィンドウの特徴を理解します。
ウィンドウの特徴 (traits) クラスは、ATL ウィンドウ オブジェクトを作成するために使用するスタイルを標準化するための単純なメソッドを提供します。 ウィンドウの特徴は、別のテンプレート パラメーターとして受け入れられます[CWindowImpl](../atl/reference/cwindowimpl-class.md)および既定のクラス レベルのウィンドウ スタイルを指定するための手段として他の ATL ウィンドウ クラスです。  
  
 ウィンドウのインスタンスの作成者が明示的に呼び出しでは、スタイルを指定しない場合[作成](../atl/reference/cwindowimpl-class.md#create)、特徴 (traits) クラスを使用すると、正しいスタイルを使用して、ウィンドウがまだ作成されたことを確認できます。 特定のスタイルが設定されているウィンドウ クラスのすべてのインスタンスの他のスタイルを許容しつつ、インスタンスごとに設定するを確認することもできます。  
  
## <a name="atl-window-traits-templates"></a>ATL ウィンドウの特徴 (traits) テンプレート  
 ATL には、コンパイル時に、テンプレート パラメーターを使用して既定のスタイルを設定することは 2 つのウィンドウ特徴 (traits) テンプレートが用意されています。  
  
|クラス|説明|  
|-----------|-----------------|  
|[CWinTraits](../atl/reference/cwintraits-class.md)|既定の呼び出しでは、他のスタイルが指定されていない場合にのみ使用されるウィンドウ スタイルを指定する場合は、このテンプレートを使用して**作成**です。 コンパイル時に実行時の優先でに設定されたスタイルを提供するスタイル。|  
|[CWinTraitsOR](../atl/reference/cwintraitsor-class.md)|ウィンドウ クラスを常に設定する必要があるスタイルを指定する場合は、このクラスを使用します。 実行時に提供するスタイルは、ビットごとの OR 演算子を使用してコンパイル時に設定するスタイルを使用して結合されます。|  
  
 ATL には、多数の特殊化の定義済みのこれらのテンプレートだけでなく、`CWinTraits`ウィンドウ スタイルの一般的に使用される組み合わせのテンプレートです。 参照してください、 [CWinTraits](../atl/reference/cwintraits-class.md)完全な詳細情報の説明を参照します。  
  
## <a name="custom-window-traits"></a>カスタムのウィンドウの特徴  
 ATL によって提供されるテンプレートの特化が 1 つは不十分なため、めったと特徴 (traits) クラスを作成する必要があります、だけを 2 つの静的関数を実装するクラスを作成する必要があります:`GetWndStyle`と**なる場合があります**:  
  
 [!code-cpp[NVC_ATL_Windowing#68](../atl/codesnippet/cpp/understanding-window-traits_1.h)]  
  
 これらの各関数に渡されるスタイル値新しいスタイルの値を生成するために使用できる実行時。 場合は、ウィンドウの特徴 (traits) クラスは、ATL ウィンドウ クラスへのテンプレート引数として使用されている、これらの静的関数に渡されるスタイル値がスタイル引数として渡されたオブジェクトになります[作成](../atl/reference/cwindowimpl-class.md#create)です。  
  
## <a name="see-also"></a>関連項目  
 [ウィンドウ クラス](../atl/atl-window-classes.md)

