---
title: CObject からクラスを派生する |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CObject
dev_langs:
- C++
helpviewer_keywords:
- DECLARE_DYNCREATE macro [MFC]
- DECLARE_SERIAL macro [MFC]
- macros [MFC], serialization
- serialization [MFC], macros
- DECLARE_DYNAMIC macro [MFC]
- derived classes [MFC], from CObject
- CObject class [MFC], deriving serializable classes
- CObject class [MFC], deriving from
ms.assetid: 5ea4ea41-08b5-4bd8-b247-c5de8c152a27
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2d0b629617c1592387f3f959996fd3e9837242ea
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="deriving-a-class-from-cobject"></a>CObject からのクラスの派生
この記事からクラスを派生する最小手順を説明する[CObject](../mfc/reference/cobject-class.md)です。 その他の`CObject`クラス アーティクル固有の仕様を活用するために必要な手順を説明する`CObject`シリアル化および診断のデバッグのサポートなどの機能です。  
  
 説明で`CObject`、"インターフェイス file"と「実装ファイル」を頻繁に使用します。 インターフェイス ファイル (多くの場合、ヘッダー ファイルと呼ばれますか。H ファイル) には、クラス宣言とその他のクラスを使用するために必要な情報が含まれています。 実装ファイル (またはします。CPP ファイル) には、クラス定義だけでなく、クラス メンバー関数を実装するコードが含まれています。 たとえば、という名前のクラス`CPerson`、一般に PERSON という名前インターフェイス ファイルを作成します。H と実装ファイルには、ユーザーがという名前です。CPP です。 ただし、アプリケーション間で共有されていない小さなクラス、インターフェイスと実装、1 つに結合して簡単があります。CPP ファイルです。  
  
 クラスを派生している場合に、機能の 4 つのレベルから選択できます`CObject`:  
  
-   基本的な機能: ランタイム クラス情報またはシリアル化のサポートが含まれていません診断メモリ管理にはします。  
  
-   基本的な機能、およびランタイム クラス情報に関するサポート。  
  
-   基本的な機能、およびランタイム クラス情報と動的な作成をサポートします。  
  
-   基本的な機能、およびランタイム クラス情報、動的な作成は、シリアル化をサポートします。  
  
 (基底クラスとして後で使用されるもの) に再利用するために設計されたクラスにはランタイム クラスのサポートとシリアル化のサポートには、少なくともを含める必要があります、将来のシリアル化の必要性が予想される場合。  
  
 宣言とから派生したクラスの実装で特定の宣言と実装マクロを使用して機能のレベルを選択する`CObject`です。  
  
 次の表は、シリアル化と実行時の情報をサポートするために使用されるマクロ間の関係を示します。  
  
### <a name="macros-used-for-serialization-and-run-time-information"></a>シリアル化と実行時の情報に使用されるマクロ  
  
|マクロを使用します。|使うため|CRuntimeClass:。<br /><br /> CreateObject|CArchive::operator >><br /><br /> CArchive::operator <<|  
|----------------|-----------------------|--------------------------------------|-------------------------------------------------------|  
|基本的な`CObject`機能|×|Ｘ|Ｘ|  
|`DECLARE_DYNAMIC`|はい|いいえ|Ｘ|  
|`DECLARE_DYNCREATE`|はい|はい|いいえ|  
|`DECLARE_SERIAL`|はい|はい|[はい]|  
  
#### <a name="to-use-basic-cobject-functionality"></a>CObject の基本的な機能を使用するには  
  
1.  クラスを派生する標準の C++ 構文を使用して`CObject`(またはから派生したクラスから`CObject`)。  
  
     次の例では、最も簡単なケースからクラスの派生`CObject`:  
  
     [!code-cpp[NVC_MFCCObjectSample#1](../mfc/codesnippet/cpp/deriving-a-class-from-cobject_1.h)]  
  
 通常、ただしは無効にするいくつかの`CObject`の新しいクラスの詳細を処理するメンバー関数。 オーバーライドする可能性があります通常など、`Dump`関数の`CObject`クラスの内容をデバッグ出力を提供します。 オーバーライドする方法の詳細について`Dump`、記事を参照して[診断: オブジェクトの内容をダンプ](http://msdn.microsoft.com/en-us/727855b1-5a83-44bd-9fe3-f1d535584b59)です。 オーバーライドすることも、`AssertValid`関数の`CObject`クラス オブジェクトのデータ メンバーの整合性の検証をカスタマイズしたテストを提供します。 オーバーライドする方法の詳細については`AssertValid`を参照してください[MFC ASSERT_VALID と cobject::assertvalid](http://msdn.microsoft.com/en-us/7654fb75-9e9a-499a-8165-0a96faf2d5e6)です。  
  
 アーティクル[機能のレベルを指定する](../mfc/specifying-levels-of-functionality.md)ランタイム クラス情報、動的なオブジェクトの作成、およびシリアル化など、機能の他のレベルを指定する方法について説明します。  
  
## <a name="see-also"></a>関連項目  
 [CObject の使い方](../mfc/using-cobject.md)

