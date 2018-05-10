---
title: WSADATA 構造体 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- WSADATA
dev_langs:
- C++
helpviewer_keywords:
- WSADATA structure [MFC]
ms.assetid: 80cc60e5-f9ae-4290-8ed5-07003136627d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 93c98f792e1d72d3e6d4a8e15b8347c653b32f46
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="wsadata-structure"></a>WSADATA 構造体
`WSADATA`への呼び出しによって返される Windows ソケットの初期化情報を格納する構造体が使用される、`AfxSocketInit`グローバル関数。  
  
## <a name="syntax"></a>構文  
  
```  
struct WSAData {  
    WORD wVersion;  
    WORD wHighVersion;  
    char szDescription[WSADESCRIPTION_LEN+1];  
    char szSystemStatus[WSASYSSTATUS_LEN+1];  
    unsigned short iMaxSockets;  
    unsigned short iMaxUdpDg;  
    char FAR* lpVendorInfo;  
};  
```  
  
#### <a name="parameters"></a>パラメーター  
 *wVersion*  
 Windows Sockets DLL を使用する、呼び出し元が必要ですが、Windows ソケット仕様のバージョン。  
  
 *wHighVersion*  
 (上記と同じエンコードも) この DLL をサポートできる Windows ソケット仕様の最大バージョン。 通常、これは、同じ**wVersion**です。  
  
 *szDescription*  
 Null で終わる ASCII 文字列を Windows Sockets DLL をコピーする仕入先 id を含む、Windows ソケットの実装の説明。 テキスト (最大 256 文字) は、任意の文字を含めることができますが、ベンダーはコントロール文字を書式設定などに対する留めて: 最も可能性の高いにこのアプリケーションが配置されるようは (おそらく切り捨てられます) 表示で、ステータス メッセージ。  
  
 *ような*  
 Null で終わる ASCII 文字列 Windows Sockets DLL が関連するステータスや構成情報をコピーする先。 情報がユーザーにとって有用であるやサポート スタッフ; 場合にのみ、Windows Sockets DLL はこのフィールドを使用する必要があります。拡張機能として考慮する必要がありますされません、 **szDescription**フィールドです。  
  
 *iMaxSockets*  
 1 つのプロセスが開くことができる可能性のあるソケットの最大数。 Windows Sockets 実装は、任意のプロセスに割り当てのソケットのグローバル プールを提供できます。代わりに、ソケットのプロセスごとのリソースを割り当て、できます。 数が、Windows Sockets DLL またはネットワーク ソフトウェアが構成された方法を反映してもあります。 アプリケーションの作成者は、端的に Windows Sockets 実装がアプリケーションで使用できるかどうかを示す値としてこの数値を使用できます。 たとえば、X Windows サーバーを確認して可能性があります**iMaxSockets**を初めて起動したときに: アプリケーションがネットワーク ソフトウェアを再構成するユーザーに指示するエラー メッセージを表示が 8 未満である場合。 (これは、状況、**ような**テキストが使用される可能性があります)。言うまでもなく、特定のアプリケーションが実際に割り当てられるという保証はありません**iMaxSockets**ソケット、他の Windows ソケット アプリケーションで使用することがあるためです。  
  
 *き*  
 送信または Windows ソケット アプリケーションで受信できる最大のユーザー データグラム プロトコル (UDP) データグラムのバイト サイズ。 実装では、制限を設定しない場合**とき**は 0 です。 Berkeley ソケットの多くの実装では、暗黙的な (これは、必要に応じてが断片化されている) UDP データグラムは 8192 バイトの制限。 Windows Sockets 実装は、インスタンスの割り当てに基づいてフラグメントの再構築のバッファーの制限を適用できます。 最小値**とき**準拠している Windows Sockets 実装は 512 です。 値に関係なく**とき**は、ネットワークの最大転送単位 (MTU) よりも大きいブロードキャスト データグラムを送信しようとすることをお勧めします。 (Windows ソケット API は、MTU を検出するためのメカニズムを提供していないが 512 バイト以上にする必要があります)。  
  
 *lpVendorInfo*  
 ベンダー固有のデータ構造体への far ポインター。 (指定された) 場合は、この構造体の定義については、Windows ソケット仕様の範囲外です。  
  
> [!NOTE]
>  MFC では、`WSADATA`構造がによって返される、`AfxSocketInit`で呼び出すことが、関数、`InitInstance`関数。 構造体を取得でき、そこから後で情報を使用する必要がある場合、プログラムで保存することができます。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** winsock2.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)

