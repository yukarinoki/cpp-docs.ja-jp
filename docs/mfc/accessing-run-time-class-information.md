---
title: ランタイム クラス情報にアクセスする |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CObject class [MFC], and RTTI
- CObject class [MFC], using IsKindOf method [MFC]
- run time [MFC], class information
- RUNTIME_CLASS macro [MFC]
- CObject class [MFC], using RUNTIME_CLASS macro [MFC]
- RTTI compiler option [MFC]
- CObject class [MFC], accessing run-time class information
- run time [MFC]
- IsKindOf method method [MFC]
- run-time class [MFC], accessing information
- classes [MFC], run-time class information
- run-time class [MFC]
- RUNTIME_CLASS macro, using
ms.assetid: 3445a9af-0bd6-4496-95c3-aa59b964570b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 947102f17a5f35b7e6b5266f637375982d4cd55f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33334062"
---
# <a name="accessing-run-time-class-information"></a>ランタイム クラス情報へのアクセス方法
この記事では、実行時にオブジェクトのクラスの情報にアクセスする方法について説明します。  
  
> [!NOTE]
>  MFC は使用しない、[実行時型情報](../cpp/run-time-type-information.md)(RTTI) サポートの Visual C 4.0 で導入されました。  
  
 クラスを派生する場合[CObject](../mfc/reference/cobject-class.md)使用して、 **DECLARE**_**動的**と`IMPLEMENT_DYNAMIC`、`DECLARE_DYNCREATE`と`IMPLEMENT_DYNCREATE`、または、 `DECLARE_SERIAL`と`IMPLEMENT_SERIAL`記事で説明されているマクロ[CObject からクラスを派生する](../mfc/deriving-a-class-from-cobject.md)、`CObject`クラスは、実行時にオブジェクトの正確なクラスを決定する権限を持ちます。  
  
 この機能は、特別な型チェック関数の引数が必要なとき、およびオブジェクトのクラスに基づく特殊なコードを記述する必要がありますに最も便利です。 ただし、この方法は通常しないで仮想関数の機能を複製します。  
  
 `CObject`メンバー関数は、`IsKindOf`を調べるには、特定のオブジェクトが、指定されたクラスに属している場合、特定のクラスから派生している場合に使用できます。 引数`IsKindOf`は、`CRuntimeClass`オブジェクトを使用して取得したことができます、`RUNTIME_CLASS`マクロ クラスの名前に置き換えます。  
  
### <a name="to-use-the-runtimeclass-macro"></a>RUNTIME_CLASS マクロを使用するには  
  
1.  使用して`RUNTIME_CLASS`クラスの次のように、クラスの名前を持つ`CObject`:  
  
     [!code-cpp[NVC_MFCCObjectSample#4](../mfc/codesnippet/cpp/accessing-run-time-class-information_1.cpp)]  
  
 ほとんどの場合は、実行時クラス オブジェクトに直接アクセスする必要です。 は一般的に使用するランタイム クラスのオブジェクトを渡し、`IsKindOf`関数は、次の手順で示すようにします。 `IsKindOf`関数は、特定のクラスに属しているかどうかに表示するオブジェクトをテストします。  
  
#### <a name="to-use-the-iskindof-function"></a>IsKindOf 関数を使用するには  
  
1.  このクラスには、ランタイム クラスのサポートを確認します。 つまり、する必要がありますがされてから派生したクラス直接的または間接的に`CObject`を使用して、 **DECLARE**_**動的**と`IMPLEMENT_DYNAMIC`、`DECLARE_DYNCREATE`と`IMPLEMENT_DYNCREATE`、または、 `DECLARE_SERIAL`と`IMPLEMENT_SERIAL`記事で説明されているマクロ[CObject からクラスを派生する](../mfc/deriving-a-class-from-cobject.md)です。  
  
2.  呼び出す、`IsKindOf`そのクラスのオブジェクトのメンバー関数を使用して、`RUNTIME_CLASS`を生成するマクロ、`CRuntimeClass`引数は、次のように。  
  
     [!code-cpp[NVC_MFCCObjectSample#2](../mfc/codesnippet/cpp/accessing-run-time-class-information_2.h)]  
  
     [!code-cpp[NVC_MFCCObjectSample#5](../mfc/codesnippet/cpp/accessing-run-time-class-information_3.cpp)]  
  
    > [!NOTE]
    >  IsKindOf 返します**TRUE**オブジェクトが指定したクラスのまたは指定したクラスから派生したクラスのメンバーである場合。 `IsKindOf` サポートしていません複数の継承または、仮想基底クラスが必要な場合に、派生の Microsoft Foundation classes の多重継承を使用することができます。  
  
 ランタイム クラス情報の用途の 1 つが、オブジェクトの動的に作成します。 この操作は、記事で説明されて[オブジェクトの動的生成](../mfc/dynamic-object-creation.md)です。  
  
 シリアル化に関する情報と、ランタイム クラス情報の詳細、記事を参照してください。 [MFC のファイル](../mfc/files-in-mfc.md)と[シリアル化](../mfc/serialization-in-mfc.md)です。  
  
## <a name="see-also"></a>関連項目  
 [CObject の使い方](../mfc/using-cobject.md)

