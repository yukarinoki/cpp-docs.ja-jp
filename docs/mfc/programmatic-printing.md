---
description: '詳細情報: プログラムによる印刷'
title: プログラムによる印刷
ms.date: 11/04/2016
helpviewer_keywords:
- printing [MFC], active documents
- active documents [MFC], printing
- printing [MFC], programmatic
- IPrint interface
- printing [MFC]
ms.assetid: 3db0945b-5e13-4be4-86a0-6aecdae565bd
ms.openlocfilehash: c97a3938a97970e1479add4f62b68250845ba7e1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97154696"
---
# <a name="programmatic-printing"></a>プログラムによる印刷

OLE では、永続的なドキュメント () を一意に識別 `GetClassFile` し、関連付けられているコード (、、 `CoCreateInstance` `QueryInterface(IID_IPersistFile)` `QueryInterface(IID_IPersistStorage)` 、 `IPersistFile::Load` 、および `IPersistStorage::Load` ) に読み込むことができました。 ドキュメントの印刷をさらに有効にするには (OLE 2.0 に付属していない既存の OLE デザインを使用する)、ドキュメント `IPrint` の種類の永続的な状態を読み込むことができる基本標準の印刷インターフェイスであるが導入されています。 アクティブなドキュメントの各ビューでは、必要に応じて、 `IPrint` これらの機能を提供するインターフェイスをサポートできます。

`IPrint` インターフェイスは、次のように定義されます。

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

クライアントとコンテナーは、を使用し `IPrint::Print` て、ドキュメントが読み込まれた後、印刷コントロールフラグ、ターゲットデバイス、印刷するページ、および追加オプションを指定して、ドキュメントを印刷するように指示します。 クライアントは、インターフェイスを使用した印刷の継続を制御することもでき `IContinueCallback` ます (下記参照)。

さらに、は、 `IPrint::SetInitialPageNum` ページにシームレスに番号を付けることによって一連のドキュメントを1つに印刷する機能をサポートしています。これは、Office バインダーのような active ドキュメントコンテナーの利点です。 `IPrint::GetPageInfo` 呼び出し元が、以前に渡された開始ページ番号 `SetInitialPageNum` (またはドキュメントの内部の既定の開始ページ番号) とドキュメント内のページ数を取得できるようにすることで、ページ割り当て情報を簡単に表示します。

をサポートするオブジェクト `IPrint` は、オブジェクトの CLSID の下に格納されている "印刷可能な" キーを使用してレジストリでマークされます。

HKEY_CLASSES_ROOT\CLSID\\ {...}\ 印刷可能

`IPrint` 通常、は、またはをサポートする同じオブジェクトに実装され `IPersistFile` `IPersistStorage` ます。 呼び出し元は、レジストリで "印刷可能" キーを検索することによって、何らかのクラスの永続的な状態をプログラムで出力する機能を備えています。 現時点では、"印刷可能" は少なくとものサポートを示して `IPrint` います。他のインターフェイスは将来定義される可能性があります。これは、で `QueryInterface` `IPrint` サポートの基本レベルを表すだけで使用できます。

印刷処理中に、印刷を開始したクライアントまたはコンテナーで印刷を続行するかどうかを制御する必要がある場合があります。 たとえば、コンテナーは、印刷ジョブをできるだけ早く終了する必要がある "印刷の停止" コマンドをサポートする場合があります。 この機能をサポートするために、印刷可能なオブジェクトのクライアントは、インターフェイスを備えた小さい通知シンクオブジェクトを実装でき `IContinueCallback` ます。

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

このインターフェイスは、Win32 API 内のさまざまな継続プロシージャの代わりに使用する、一般的な継続コールバック関数として使用できるように設計されています (たとえば、 `AbortProc` 印刷用の、 `EnumMetafileProc` for metafile 列挙型など)。 したがって、このインターフェイスの設計は、時間のかかるさまざまなプロセスで役に立ちます。

最も一般的なケースでは、 `IContinueCallback::FContinue` 関数は時間のかかるプロセスによって定期的に呼び出されます。 シンクオブジェクトは S_OK を返して操作を続行し、S_FALSE してできるだけ早くプロシージャを停止します。

`FContinue`ただし、のコンテキストでは使用されません。印刷ではを `IPrint::Print` 使用 `IContinueCallback::FContinuePrint` します。 印刷オブジェクトは、 `FContinuePrinting` 印刷されたページの数、印刷されるページの数、およびクライアントがユーザーに表示する印刷ステータスを示す追加文字列 (たとえば、"ページ 5/19") を定期的に呼び出す必要があります。

## <a name="see-also"></a>関連項目

[Active ドキュメントコンテナー](../mfc/active-document-containers.md)
