---
description: 詳細については、「ATL オブジェクトの Noncreatable」を参照してください。
title: ATL オブジェクトを作成できないようにする
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.ATL.objects
helpviewer_keywords:
- noncreatable ATL objects
- ATL projects, noncreatable objects
ms.assetid: 80d0bca2-dea0-4801-9a85-6243124437f6
ms.openlocfilehash: 0a7a07081546722e5a960cb8bf0384a1d7e47f9b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97139179"
---
# <a name="making-an-atl-object-noncreatable"></a>ATL オブジェクトを作成できないようにする

ATL ベースの COM オブジェクトの属性を変更して、クライアントがオブジェクトを直接作成できないようにすることができます。 この場合、オブジェクトは、直接作成されるのではなく、別のオブジェクトに対するメソッド呼び出しによって返されます。

## <a name="to-make-an-object-noncreatable"></a>オブジェクトを noncreatable にするには

1. オブジェクトの [OBJECT_ENTRY_AUTO](object-map-macros.md#object_entry_auto) を削除します。 オブジェクトを noncreatable にして、コントロールを登録する場合は、OBJECT_ENTRY_AUTO を [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](object-map-macros.md#object_entry_non_createable_ex_auto)に置き換えます。

1. [Noncreatable](../../windows/attributes/noncreatable.md)属性を .idl ファイル内のコクラスに追加します。 次に例を示します。

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

[ATL プロジェクト ウィザード](../../atl/reference/atl-project-wizard.md)<br/>
[Visual Studio の C++ プロジェクトの種類](../../build/reference/visual-cpp-project-types.md)<br/>
[ATL および C Run-Time コードを使用したプログラミング](../../atl/programming-with-atl-and-c-run-time-code.md)<br/>
[ATL COM オブジェクトの基礎](../../atl/fundamentals-of-atl-com-objects.md)<br/>
[既定の ATL プロジェクト構成](../../atl/reference/default-atl-project-configurations.md)
