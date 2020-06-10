---
title: ドキュメント テンプレートの作成
ms.date: 11/04/2016
helpviewer_keywords:
- document templates [MFC]
- constructors [MFC], document template
- document templates [MFC], creating
- MFC, document templates
- templates [MFC], document templates
ms.assetid: c87f1821-7cbf-442e-9690-f126ae7fb783
ms.openlocfilehash: 952a383792eb3a4d0a4ed1b3e24dd82f7fa644cf
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84615793"
---
# <a name="document-template-creation"></a>ドキュメント テンプレートの作成

[**ファイル**] メニューから新規または**開い**ているコマンドに応答して新しいドキュメントを作成する場合、ドキュメントテンプレート**では、** ドキュメントを表示するための新しいフレームウィンドウも作成されます。

ドキュメントテンプレートコンストラクターは、テンプレートが作成できるドキュメント、ウィンドウ、およびビューの種類を指定します。 これは、ドキュメントテンプレートコンストラクターに渡す引数によって決まります。 次のコードは、サンプルアプリケーションの[CMultiDocTemplate](reference/cmultidoctemplate-class.md)を作成する方法を示しています。

[!code-cpp[NVC_MFCDocView#7](codesnippet/cpp/document-template-creation_1.cpp)]

新しいオブジェクトへのポインター `CMultiDocTemplate` は、 [、adddoctemplate](reference/cwinapp-class.md#adddoctemplate)の引数として使用されます。 コンストラクターへの引数には、 `CMultiDocTemplate` ドキュメントの種類のメニューとアクセラレータに関連付けられているリソース ID と、3つの[RUNTIME_CLASS](reference/run-time-object-model-services.md#runtime_class)マクロの使用が含まれます。 `RUNTIME_CLASS`という名前の C++ クラスの[CRuntimeClass](reference/cruntimeclass-structure.md)オブジェクトを引数として返します。 ドキュメントテンプレートコンストラクターに渡された3つのオブジェクトは、 `CRuntimeClass` ドキュメント作成プロセス中に、指定したクラスの新しいオブジェクトを作成するために必要な情報を提供します。 この例では、オブジェクトがアタッチされたオブジェクトを作成するドキュメントテンプレートの作成を示し `CScribDoc` `CScribView` ます。 ビューは、標準の MDI 子フレームウィンドウによってフレーム表示されます。

## <a name="see-also"></a>関連項目

[ドキュメントテンプレートとドキュメント/ビュー作成プロセス](document-templates-and-the-document-view-creation-process.md)<br/>
[ドキュメントおよびビューの作成](document-view-creation.md)<br/>
[MFC オブジェクト間の関係](relationships-among-mfc-objects.md)<br/>
[新しいドキュメント、ウィンドウ、およびビューの作成](creating-new-documents-windows-and-views.md)
