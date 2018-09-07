---
title: ATL オブジェクトを作成できないように |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.appwiz.ATL.objects
dev_langs:
- C++
helpviewer_keywords:
- noncreatable ATL objects
- ATL projects, noncreatable objects
ms.assetid: 80d0bca2-dea0-4801-9a85-6243124437f6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4a77ed656d39888e85e607ee4fdd96b384d0d250
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43761457"
---
# <a name="making-an-atl-object-noncreatable"></a>ATL オブジェクトを作成できないをこと

ATL ベースの COM オブジェクトの属性を変更するには、クライアントからオブジェクトを直接作成することはできませんようにします。 この場合、オブジェクトが別のオブジェクトのメソッドの呼び出しによって返されるのではなく直接作成します。

### <a name="to-make-an-object-noncreatable"></a>オブジェクトを作成できないようにするには

1. 削除、 [OBJECT_ENTRY_AUTO](object-map-macros.md#object_entry_auto)オブジェクト。 Noncreatable が登録するコントロール オブジェクトを実行する場合に、置換と OBJECT_ENTRY_AUTO[役立つ](object-map-macros.md#object_entry_non_createable_ex_auto)します。

2. 追加、 [noncreatable](../../windows/noncreatable.md) .idl ファイルのコクラスの属性します。 例えば:

    ```  
    [uuid(A1992E3D-3CF0-11D0-826F-00A0C90F2851), 
    helpstring("MyObject"), 
    noncreatable]  
    coclass MyObject  
    {  
        [default] interface IMyInterface;  
    }  
    ```

## <a name="see-also"></a>関連項目

[ATL プロジェクト ウィザード](../../atl/reference/atl-project-wizard.md)   
[Visual C++ プロジェクトの種類](../../ide/visual-cpp-project-types.md)   
[アプリケーション ウィザードを使用したデスクトップ プロジェクトの作成](../../ide/creating-desktop-projects-by-using-application-wizards.md)   
[ATL および C ランタイム コードによるプログラミング](../../atl/programming-with-atl-and-c-run-time-code.md)   
[ATL COM オブジェクトの基礎](../../atl/fundamentals-of-atl-com-objects.md)   
[ATL プロジェクトの既定の構成](../../atl/reference/default-atl-project-configurations.md)

