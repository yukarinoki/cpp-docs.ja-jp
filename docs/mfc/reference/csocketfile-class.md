---
title: CSocketFile クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSocketFile
- AFXSOCK/CSocketFile
- AFXSOCK/CSocketFile::CSocketFile
dev_langs:
- C++
helpviewer_keywords:
- CSocketFile [MFC], CSocketFile
ms.assetid: 7924c098-5f72-40d6-989d-42800a47958f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4f1198c85b8366d7dec4d38d002b65468c38347c
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2018
ms.locfileid: "37121730"
---
# <a name="csocketfile-class"></a>CSocketFile クラス
Windows ソケットを使ったネットワーク間でのデータの送受信に使われる `CFile` オブジェクトです。  
  
## <a name="syntax"></a>構文  
  
```  
class CSocketFile : public CFile  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CSocketFile::CSocketFile](#csocketfile)|`CSocketFile` オブジェクトを構築します。|  
  
## <a name="remarks"></a>Remarks  
 アタッチすることができます、`CSocketFile`オブジェクトを`CSocket`この目的のオブジェクト。 してアタッチするには、通常、`CSocketFile`オブジェクトを`CArchive`MFC のシリアル化を使用してデータの送受信を簡略化するオブジェクト。  
  
 (送信) のデータをシリアル化するに挿入する、アーカイブ`CSocketFile`データを書き込むメンバー関数、`CSocket`オブジェクト。 逆シリアル化する (受信) アーカイブから抽出するデータ。 これが原因で、アーカイブを呼び出す`CSocketFile`からデータを読み取るメンバー関数、`CSocket`オブジェクト。  
  
> [!TIP]
>  使用するだけでなく`CSocketFile`」の説明に従って、として使用できますが、スタンドアロンのファイル オブジェクトと同様`CFile`、その基本クラスです。 使用することも`CSocketFile`アーカイブ ベースの MFC シリアル化関数とします。 `CSocketFile`すべてのサポートされない`CFile`機能、MFC の既定のシリアル化の関数と互換性がない`CSocketFile`です。 これは特に、`CEditView`クラスです。 シリアル化しないでください`CEditView`を使用してデータを`CArchive`オブジェクトに関連付けられて、`CSocketFile`オブジェクトを使用して`CEditView::SerializeRaw`; を使用して`CEditView::Serialize`代わりにします。 `SerializeRaw`関数など、関数に、ファイル オブジェクトが必要ですが`Seek`、その`CSocketFile`はありません。  
  
 使用する場合`CArchive`で`CSocketFile`と`CSocket`、状況が発生する可能性があります、`CSocket::Receive`ループに入る (によって`PumpMessages(FD_READ)`) 要求されたバイト数を待機しています。 これは、Windows ソケット FD_READ 通知ごとに 1 つだけの受信呼び出しを許可するため、`CSocketFile`と`CSocket`FD_READ ごとの複数の受信呼び出しができるようにします。 表示された場合、FD_READ 読み取るデータがない場合に、アプリケーションがハングします。 別の FD_READ を取得しない場合、アプリケーションは、ソケット上で通信を停止します。  
  
 次のようにこの問題を解決できます。 `OnReceive`ソケット クラス、呼び出しのメソッド`CAsyncSocket::IOCtl(FIONREAD, ...)`を呼び出す前に、`Serialize`ソケットから読み取る必要なデータが 1 つの TCP パケット ネットワーク メディアの (最大転送単位のサイズを超える場合、メッセージ クラスのメソッド、通常 1096 バイト以上)。 使用可能なデータのサイズが必要なよりも小さい場合は、すべてのデータを受信して、読み取り操作を開始して待機します。  
  
 次の例では、`m_dwExpected`ユーザーが受信されるバイトのおおよその数です。 宣言している他の場所で、コード内と見なされます。  
  
 [!code-cpp[NVC_MFCSocketThread#4](../../mfc/reference/codesnippet/cpp/csocketfile-class_1.cpp)]  
  
 詳細については、次を参照してください。 [MFC における Windows ソケット](../../mfc/windows-sockets-in-mfc.md)、 [Windows ソケット: アーカイブ付きソケットの使用](../../mfc/windows-sockets-using-sockets-with-archives.md)、だけでなく[Windows Sockets 2 API](http://msdn.microsoft.com/library/windows/desktop/ms740673)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 `CSocketFile`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxsock.h  
  
##  <a name="csocketfile"></a>  CSocketFile::CSocketFile  
 `CSocketFile` オブジェクトを構築します。  
  
```  
explicit CSocketFile(
    CSocket* pSocket,  
    BOOL bArchiveCompatible = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 *pSocket*  
 アタッチするソケット、`CSocketFile`オブジェクト。  
  
 *で*  
 ファイル オブジェクトで使用するかどうかを指定、`CArchive`オブジェクト。 パスを使用する場合にのみ、`CSocketFile`スタンドアロンと同様に、スタンドアロンの方法でオブジェクト`CFile`オブジェクト、制限事項があります。 このフラグは変更する方法、`CArchive`オブジェクトに関連付けられて、`CSocketFile`オブジェクトは読み取り用のバッファーを管理します。  
  
### <a name="remarks"></a>Remarks  
 このオブジェクトのデストラクターの関連付けを解除自体ソケット オブジェクトから、オブジェクトがスコープ外に出るか、削除時にします。  
  
> [!NOTE]
>  A`CSocketFile`なし (制限あり) ファイルとしても使用できます、`CArchive`オブジェクト。 既定では、`CSocketFile`コンス トラクターの*で*パラメーターは TRUE です。 これは、アーカイブで使用するのファイル オブジェクトであることを指定します。 使用する、アーカイブせずに、ファイル オブジェクトを渡しますで FALSE、*で*パラメーター。  
  
 その「アーカイブ互換性のある」モードで、`CSocketFile`オブジェクトは、パフォーマンスを向上させると、「デッドロック」の危険性を軽減 デッドロックは、送信側と受信側の両方のソケットは、互いにまたは一般的なリソースを待機しているときに発生します。 場合に、このような状況が発生する可能性があります、`CArchive`と協力して、オブジェクト、`CSocketFile`は方法、`CFile`オブジェクト。 `CFile`アーカイブを受信した場合、要求したバイト数、ファイルの末尾に達していると見なすことできます。  
  
 `CSocketFile`、ただし、データはメッセージ ベース以外の場合は、バッファーは、複数のメッセージを含めることができます、ように受信要求バイト数より少ないファイルの終わりを意味しません。 アプリケーションとそれほど、ここではブロックしません`CFile`バッファーが空になるまで、バッファーからメッセージの読み取りを続行するとします。 [CArchive::IsBufferEmpty](../../mfc/reference/carchive-class.md#isbufferempty)関数は、このような場合、アーカイブのバッファーの状態を監視するために役立ちます。  
  
 使用の詳細については`CSocketFile`、記事を参照して[Windows ソケット: アーカイブ付きソケットの使用](../../mfc/windows-sockets-using-sockets-with-archives.md)と[Windows ソケット: 例のソケットを使用してアーカイブ](../../mfc/windows-sockets-example-of-sockets-using-archives.md)です。  
  
## <a name="see-also"></a>関連項目  
 [CFile クラス](../../mfc/reference/cfile-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CAsyncSocket クラス](../../mfc/reference/casyncsocket-class.md)   
 [CSocket クラス](../../mfc/reference/csocket-class.md)
