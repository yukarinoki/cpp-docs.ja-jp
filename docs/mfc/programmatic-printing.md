---
title: プログラムによる印刷 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- printing [MFC], active documents
- active documents [MFC], printing
- printing [MFC], programmatic
- IPrint interface
- printing [MFC]
ms.assetid: 3db0945b-5e13-4be4-86a0-6aecdae565bd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dbbc9792fcaec6713e13b4665568017bc5ce1bdc
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2018
ms.locfileid: "36930928"
---
# <a name="programmatic-printing"></a>プログラムによる印刷
OLE が永続的なドキュメントを一意に識別するための手段を提供 (`GetClassFile`) と、関連付けられているコードへのロード (`CoCreateInstance`、 `QueryInterface(IID_IPersistFile)`、 `QueryInterface(IID_IPersistStorage)`、 `IPersistFile::Load`、および`IPersistStorage::Load`)。 Active ドキュメント コンテインメント (OLE 2.0 に付属していない既存の OLE デザインを使用して) ドキュメントの印刷をさらに有効にするにはベースの標準の印刷インターフェイスが導入されています`IPrint`、読み込むことができる任意のオブジェクトで一般的に使用できる、ドキュメントの種類の永続的な状態です。 アクティブ ドキュメントの各ビューをサポートできます必要に応じて、`IPrint`これらの機能を提供するインターフェイスです。  
  
 `IPrint`インターフェイスは次のように定義します。  
  
```  
interface IPrint : IUnknown  
    {  
    HRESULT SetInitialPageNum([in] LONG nFirstPage);  
    HRESULT GetPageInfo(  
        [out] LONG *pnFirstPage,  
        [out] LONG *pcPages);  
    HRESULT Print(  
        [in] DWORD grfFlags,  
        [in,out] DVTARGETDEVICE **pptd,  
        [in,out] PAGESET ** ppPageSet,  
        [in,out] STGMEDIUM **ppstgmOptions,  
        [in] IContinueCallback* pCallback,  
        [in] LONG nFirstPage,  
        [out] LONG *pcPagesPrinted,  
        [out] LONG *pnPageLast);  
    };  
```  
  
 クライアントとコンテナーを使って単に`IPrint::Print`にそのドキュメントが読み込まれると、印刷コントロール フラグ、ターゲット デバイス、印刷するページを指定することは、それ自体を印刷するドキュメントの指示とその他のオプションです。 クライアントは、インターフェイスを介して印刷の継続タスクを制御できますも`IContinueCallback`(下記参照)。  
  
 さらに、`IPrint::SetInitialPageNum`番号によって 1 つのページにシームレスに明らかに Office バインダーのように active ドキュメント コンテナー用の特典として、一連のドキュメントを印刷する機能をサポートします。 `IPrint::GetPageInfo` 開始を取得する呼び出し元を許可することで簡単な改ページ情報を表示するページ番号が以前に渡される`SetInitialPageNum`(またはドキュメントの内部既定のページ番号を開始) と、ドキュメント内のページの数。  
  
 オブジェクトをサポートする`IPrint`オブジェクトの CLSID の下に格納された"Printable"キーにレジストリにマークされます。  
  
 Hkey_classes_root \clsid\\{...}\Printable  
  
 `IPrint` いずれかをサポートする同じオブジェクトに実装されて通常`IPersistFile`または`IPersistStorage`です。 呼び出し元は、"Printable"キーのレジストリで永続的な状態のいずれかのクラスをプログラムによって印刷する機能を確認します。 現時点では、「印刷可能」のサポートを指定には、少なくとも`IPrint`; 他のインターフェイス定義することも、今後使用し、れる`QueryInterface`場所`IPrint`単に基本的なレベルのサポートを表します。  
  
 印刷処理中にクライアントまたは印刷の継続するかどうかを制御する印刷を開始したコンテナーしたい場合があります。 たとえば、コンテナーは、"停止 Print"コマンドをできるだけ早く、印刷ジョブを終了する必要がありますをサポートする場合があります。 この機能をサポートするために印刷可能なオブジェクトのクライアントが小さな通知シンク オブジェクト インターフェイスを実装できます`IContinueCallback`:  
  
```  
interface IContinueCallback : IUnknown  
    {  
    HRESULT FContinue(void);  
    HRESULT FContinuePrinting(  
        [in] LONG cPagesPrinted,  
        [in] LONG nCurrentPage,  
        [in] LPOLESTR pszPrintStatus);  
    };  
```  
  
 このインターフェイスがさまざまな継続タスク手順では、Win32 API の代わりに使用されるジェネリック継続コールバック関数として役に立つに設計されています (など、`AbortProc`印刷用および`EnumMetafileProc`メタファイルの列挙のため)。 したがってこのインターフェイスの設計は、さまざまな時間のかかるプロセスに役立ちます。  
  
 ほとんどのジェネリックの場合、`IContinueCallback::FContinue`関数が時間のかかるプロセスにより定期的に呼び出されます。 シンク オブジェクトは、S_OK、操作を続行して、プロシージャをできるだけ早く停止する S_FALSE を返します。  
  
 `FContinue`、ただし、、のコンテキストでは使用されません`IPrint::Print`以外ではなく、使用して印刷`IContinueCallback::FContinuePrint`です。 任意の印刷オブジェクトを定期的に呼び出す必要があります`FContinuePrinting`印刷ページの数、印刷されるページの数と、クライアントは"ページなどのユーザーに表示したりできます印刷の状態を示す文字列を渡す5 の 19 インチ)。  
  
## <a name="see-also"></a>関連項目  
 [Active ドキュメント コンテナー](../mfc/active-document-containers.md)

