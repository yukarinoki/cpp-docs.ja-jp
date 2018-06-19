---
title: コンテナー内のウィンドウを使用して |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ATL, windows
- windows [C++], ATL
- contained windows in ATL
ms.assetid: 7b3d79e5-b569-413f-9b98-df4f14efbe2b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f6c3b439baf05c4e4287613e9b6b5a9b1c2546b6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32357922"
---
# <a name="using-contained-windows"></a>コンテナー内のウィンドウを使用します。
ATL の実装に含まれている windows [CContainedWindowT](../atl/reference/ccontainedwindowt-class.md)です。 コンテナー内のウィンドウでは、そのメッセージを独自のクラスで扱い、コンテナー オブジェクトをデリゲートするウィンドウを表します。  
  
> [!NOTE]
>  クラスを派生する必要はありません`CContainedWindowT`コンテナー内のウィンドウを使用するためにします。  
  
 コンテナー内のウィンドウでは、既存の Windows クラスまたは既存のウィンドウをサブクラス化スーパークラス化をできます。 ウィンドウをスーパークラス化する既存のウィンドウを作成するクラス、最初のコンス トラクターで既存のクラス名を指定、`CContainedWindowT`オブジェクト。 呼び出す`CContainedWindowT::Create`です。 既存のウィンドウをサブクラス化する、ウィンドウ クラス名を指定する必要はありません (渡す**NULL**コンス トラクターに)。 呼び出すだけで、`CContainedWindowT::SubclassWindow`サブクラス化されているウィンドウのハンドルを持つメソッドです。  
  
 コンテナー クラスのデータ メンバーとして含まれている windows を通常使用するとします。 コンテナーはウィンドウ以外である必要はありません。ただしから派生させる必要があります[CMessageMap](../atl/reference/cmessagemap-class.md)です。  
  
 コンテナー内のウィンドウでは、代替のメッセージ マップを使用して、そのメッセージを処理します。 1 つ以上含まれているウィンドウがあれば、いくつかの別のコンテナー内のウィンドウに対応する各メッセージ マップを宣言する必要があります。  
  
## <a name="example"></a>例  
 2 つ含まれている windows のコンテナー クラスの例を次に示します。  
  
 [!code-cpp[NVC_ATL_Windowing#67](../atl/codesnippet/cpp/using-contained-windows_1.h)]  
  
 コンテナー内のウィンドウの詳細については、次を参照してください。、 [SUBEDIT](../visual-cpp-samples.md)サンプルです。  
  
## <a name="see-also"></a>関連項目  
 [ウィンドウ クラス](../atl/atl-window-classes.md)

