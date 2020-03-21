---
title: MFC ActiveX コントロール コンテナーの作成
ms.date: 09/12/2018
f1_keywords:
- vc.appwiz.activex.container
helpviewer_keywords:
- MFC ActiveX controls [MFC], containers
- ActiveX control containers [MFC], creating
- containers [MFC], creating
- OLE controls [MFC], containers
ms.assetid: ec70e137-7c14-4940-bd0e-fd4edcc63ea5
ms.openlocfilehash: 27f229a23595d4842a77409a3cedc7a57aa43e6c
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "80079437"
---
# <a name="creating-an-mfc-activex-control-container"></a>MFC ActiveX コントロール コンテナーの作成

ActiveX コントロールコンテナーは、ActiveX (旧称 OLE) コントロールを実行するための環境を提供する親プログラムです。 MFC を使用するかどうかにかかわらず、ActiveX コントロールを含むことができるアプリケーションを作成できますが、MFC を使用する方がはるかに簡単です。

>[!IMPORTANT]
> ActiveX は、新しい開発には使用しない従来のテクノロジです。 ActiveX を置き換える最新テクノロジの詳細については、「 [Activex コントロール](../activex-controls.md)」を参照してください。

Mfc[アプリケーションウィザード](../../mfc/reference/mfc-application-wizard.md)を使用して mfc コンテナープログラムを作成すると、Mfc および activex クラスによって実装される activex コントロールとオートメーションの多くの機能にアクセスできます。 これらの機能には、ビジュアル編集、オートメーション、複合ファイルの作成、およびコントロールのサポートが含まれます。 親プログラムでサポートされる、MFC アプリケーションウィザードのビジュアル編集オプションには、コンテナー、ミニサーバー、フルサーバー、およびコンテナーとサーバーの両方であるプログラムの作成が含まれます。

- **新しい MFC アプリケーション**。 オートメーション、ビジュアル編集、複合ファイル、またはコントロールのサポートを含む新しい MFC プログラムを作成するには、MFC アプリケーションウィザードを使用して、適切なオートメーションオプションを選択します。

- **既存の MFC アプリケーション**。 既存の MFC アプリケーションにコントロールコンテインメントを追加する場合は、「 [Ole コントロールコンテナー: 手動による Ole コントロールコンテインメントの有効化](../../mfc/activex-control-containers-manually-enabling-activex-control-containment.md)」を参照してください。

### <a name="to-create-an-activex-container-for-any-of-the-following-types-of-applications"></a>次のいずれかの種類のアプリケーション用の ActiveX コンテナーを作成するには

1. [Containers](../../mfc/containers.md)

1. [ビジュアル編集](../../mfc/ole-mfc.md)

1. [MFC ActiveX コントロール](../../mfc/mfc-activex-controls.md)

## <a name="see-also"></a>参照

[Visual Studio の C++ プロジェクトの種類](../../build/reference/visual-cpp-project-types.md)
