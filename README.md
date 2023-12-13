# RPL2
<h3> Nama : Abdul Aziz
<br> Kelas Ti.22.A.1
<br>Nim :312210022
<br>Matakuliah : Rekayasa Perangkat Lunak</h3>


<h2><br> Pengembangan Sistem Gudang</h2>

# Menu Login
![image](https://github.com/lampubohlam/RPL2/assets/116137169/51fb1ec4-e770-4c18-9943-4815d9cc19cb)

 <h3>berikut tampilan Codingnya</h3> 
                                     <?php
                      require 'function.php';
                      
                      
                      //cek login, terdaftar atau tidak
                      
                      if(isset($_POST['login'])){
                          $username =($_POST['username']);
                          $password = ($_POST['password']);
                      
                      
                          //mencocokan database
                          $cekdatabase = mysqli_query($conn, "SELECT * FROM login WHERE username='$username' AND password='$password'");
                      
                          //hitung ada atau tidak
                          $hitung = mysqli_num_rows($cekdatabase);
                      
                          if($hitung>0){
                              $_SESSION['log'] ='True';
                      
                             header('location:index.php');
                          } else{
                              header('location:login.php');
                          };
                      };
                      
                      if(!isset($_SESSION['log'])){
                      
                      } else{
                          header('location:index.php');
                      }
                      
                      ?>
                       
                          
                      
                      <!DOCTYPE html>
                      <html lang="en">
                          <head>
                              <meta charset="utf-8" />
                              <meta http-equiv="X-UA-Compatible" content="IE=edge" />
                              <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no" />
                              <meta name="description" content="" />
                              <meta name="author" content="" />
                              <title>login</title>
                              <link href="css/styles.css" rel="stylesheet" />
                              <script src="https://use.fontawesome.com/releases/v6.3.0/js/all.js" crossorigin="anonymous"></script>
                          </head>
                          <body style="background-image: url('gudang.jpg'); background-size: cover;" class="bg-primary">
                              <div id="layoutAuthentication">
                                  <div id="layoutAuthentication_content">
                                      <main>
                                          <div class="container">
                                              <div class="row justify-content-center">
                                                  <div class="col-lg-5">
                                                      <div class="card shadow-lg border-0 rounded-lg mt-5">
                                                          <div class="card-header"><h3 class="text-center font-weight-light my-4">Login</h3></div>
                                                          <div class="card-body">
                                                              <form method="post">
                                                                  <div class="form-floating mb-3">
                                                                      <input class="form-control" name="username" id="inputUsername" type="username" placeholder="enter username" />
                                                                      <label for="username">masukan Username</label>
                                                                  </div>
                                                                  <div class="form-floating mb-3">
                                                                      <input class="form-control" name="password" id="inputPassword" type="password" placeholder="enter Password" />
                                                                      <label for="password">Password</label>
                                                                  </div>
                                                                  
                                                                  <div class="d-flex align-items-center justify-content-between mt-4 mb-0">
                                                                      
                                                                      <button class="btn btn-primary" name="login">Login</button>
                                                                  </div>
                                                              </form>
                                                          </div>
                                                          
                                                      </div>
                                                  </div>
                                              </div>
                                          </div>
                                      </main>
                                  </div>
                                  
                              </div>
                              <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.2.3/dist/js/bootstrap.bundle.min.js" crossorigin="anonymous"></script>
                              <script src="js/scripts.js"></script>
                          </body>
                      </html>


# Menu Utama Barang keluar
![image](https://github.com/lampubohlam/RPL2/assets/116137169/07146c92-ad4a-430b-86b9-a4a102148af3)


                                                                    <?php
                                    require 'function.php';
                                    require 'cek.php';
                                    ?>
                                    
                                    <!DOCTYPE html>
                                    <html lang="en">
                                        <head>
                                            <meta charset="utf-8" />
                                            <meta http-equiv="X-UA-Compatible" content="IE=edge" />
                                            <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no" />
                                            <meta name="description" content="" />
                                            <meta name="author" content="" />
                                            <title>Barang Keluar</title>
                                            <link href="https://cdn.jsdelivr.net/npm/simple-datatables@7.1.2/dist/style.min.css" rel="stylesheet" />
                                            <link href="css/styles.css" rel="stylesheet" />
                                            <script src="https://use.fontawesome.com/releases/v6.3.0/js/all.js" crossorigin="anonymous"></script>
                                        </head>
                                        <body class="sb-nav-fixed">
                                            <nav class="sb-topnav navbar navbar-expand navbar-dark bg-dark">
                                                <!-- Navbar Brand-->
                                                <a class="navbar-brand ps-3" href="index.php">GUDANG MANTAF</a>
                                                <!-- Sidebar Toggle-->
                                                <button class="btn btn-link btn-sm order-1 order-lg-0 me-4 me-lg-0" id="sidebarToggle" href="#!"><i class="fas fa-bars"></i></button>
                                                <!-- Navbar Search-->
                                                <form class="d-none d-md-inline-block form-inline ms-auto me-0 me-md-3 my-2 my-md-0">
                                                    <div class="input-group">
                                                        <input class="form-control" type="text" placeholder="Search for..." aria-label="Search for..." aria-describedby="btnNavbarSearch" />
                                                        <button class="btn btn-primary" id="btnNavbarSearch" type="button"><i class="fas fa-search"></i></button>
                                                    </div>
                                                </form>
                                                
                                            </nav>
                                            <div id="layoutSidenav">
                                                <div id="layoutSidenav_nav">
                                                    <nav class="sb-sidenav accordion sb-sidenav-dark" id="sidenavAccordion">
                                                        <div class="sb-sidenav-menu">
                                                            <div class="nav">
                                                                
                                                            <a class="nav-link" href="index.php">
                                                                    <div class="sb-nav-link-icon"><i class="fas fa-tachometer-alt"></i></div>
                                                                    Stock Barang
                                                                </a>
                                                                <a class="nav-link" href="masuk.php">
                                                                    <div class="sb-nav-link-icon"><i class="fas fa-tachometer-alt"></i></div>
                                                                    Barang Masuk
                                                                </a>
                                                                <a class="nav-link" href="keluar.php">
                                                                    <div class="sb-nav-link-icon"><i class="fas fa-tachometer-alt"></i></div>
                                                                    Barang Keluar
                                                                </a>
                                    
                                                                <a class="nav-link" href="logout.php">
                                                                    <div class="sb-nav-link-icon"><i class="fas fa-tachometer-alt"></i></div>
                                                                    Logout
                                                                </a>
                                    
                                    
                                                            </div>
                                                        </div>
                                                        <div class="sb-sidenav-footer">
                                                            <div class="small">Logged in as:</div>
                                                            Abdul Aziz
                                                        </div>
                                                    </nav>
                                                </div>
                                                <div id="layoutSidenav_content">
                                                    <main>
                                                        <div class="container-fluid px-4">
                                                            <h1 class="mt-4">Barang Keluar</h1>
                                                            
                                                            
                                                            <div class="card mb-4">
                                                                <div class="card-header">
                                    
                                    
                                                                <button type="button" class="btn btn-primary" data-bs-toggle="modal" data-bs-target="#myModal">
                                                                Tambah Barang
                                                                </button>
                                            
                                                                </div>
                                                                <div class="card-body">
                                                                    <div class="table-responsive">
                                                                        <table class="table table-bordered" id="dataTable" width="100%" cellspacing="0">
                                                                        <thead>
                                                                            <tr>
                                                                                <th>No</th>
                                                                                <th>Nama Barang</th>
                                                                                <th>Deskripsi</th>
                                                                                <th>Stock</th>
                                                                        
                                                                            </tr>
                                                                        </thead>
                                                                        <tbody>
                                                                            <tr>
                                                                                <td>Tiger Nixon</td>
                                                                                <td>System Architect</td>
                                                                                <td>Edinburgh</td>
                                                                                <td>61</td>
                                                                                
                                                                            </tr>
                                                                            
                                                                        </tbody>
                                                                    </table>
                                                                </div>
                                                            </div>
                                                        </div>
                                                    </main>
                                                    <footer class="py-4 bg-light mt-auto">
                                                        <div class="container-fluid px-4">
                                                            <div class="d-flex align-items-center justify-content-between small">
                                                                <div class="text-muted">Copyright &copy; Your Website 2023</div>
                                                                <div>
                                                                    <a href="#">Privacy Policy</a>
                                                                    &middot;
                                                                    <a href="#">Terms &amp; Conditions</a>
                                                                </div>
                                                            </div>
                                                        </div>
                                                    </footer>
                                                </div>
                                            </div>
                                            <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.2.3/dist/js/bootstrap.bundle.min.js" crossorigin="anonymous"></script>
                                            <script src="js/scripts.js"></script>
                                            <script src="https://cdnjs.cloudflare.com/ajax/libs/Chart.js/2.8.0/Chart.min.js" crossorigin="anonymous"></script>
                                            <script src="assets/demo/chart-area-demo.js"></script>
                                            <script src="assets/demo/chart-bar-demo.js"></script>
                                            <script src="https://cdn.jsdelivr.net/npm/simple-datatables@7.1.2/dist/umd/simple-datatables.min.js" crossorigin="anonymous"></script>
                                            <script src="js/datatables-simple-demo.js"></script>
                                        </body>
                                    
                                               <!-- The Modal -->
                                               <div class="modal fade" id="myModal">
                                                <div class="modal-dialog">
                                                    <div class="modal-content">
                                    
                                                    <!-- Modal Header -->
                                                    <div class="modal-header">
                                                        <h4 class="modal-title">Tambah Barang Keluar</h4>
                                                        <button type="button" class="btn-close" data-bs-dismiss="modal"></button>
                                                    </div>
                                    
                                    
                                    
                                                    <!-- Modal body -->
                                                    <form method="post">
                                                    <div class="modal-body">
                                                    <select name="barangnya" class="form-control">
                                                            <?php
                                                            $ambilsemuadatanya = mysqli_query($conn,"select * from stock");
                                                            while($fetcharray = mysqli_fetch_array($ambilsemuadatanya)){
                                                                $namabarangnya = $fetcharray['namabarang'];
                                                                $idbarangnya = $fetcharray['idbarang'];
                                    
                                                            ?>
                                    
                                                            <option value="<?=$idbarangnya;?>"><?=$namabarangnya;?></option>
                                    
                                    
                                                            <?php
                                                                 }
                                                            ?>
                                                        </select>
                                                        <br>
                                                        <input type="number" name="qty" placeholder="Quantity" class="form-control" required>
                                                        <br>
                                                        <input type="text" name="penerima" placeholder="Penerima" class="form-control"required>
                                                        <br>
                                                        <button type="submit" class="btn btn-primary" name="addbarangkeluar">Submit</button>
                                    
                                                    </div>
                                                    </form>
                                    
                                                </div>
                                        </div>
                                    </html>



# Tampilan Menu Index 
![image](https://github.com/lampubohlam/RPL2/assets/116137169/e127f5f6-be34-4163-bb7b-d9333e4620af)


                                <?php
                                require 'function.php';
                                require 'cek.php';
                                ?>
                                
                                <!DOCTYPE html>
                                <html lang="en">
                                    <head>
                                        <meta charset="utf-8" />
                                        <meta http-equiv="X-UA-Compatible" content="IE=edge" />
                                        <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no" />
                                        <meta name="description" content="" />
                                        <meta name="author" content="" />
                                        <title>Stock Barang</title>
                                        <link href="https://cdn.jsdelivr.net/npm/simple-datatables@7.1.2/dist/style.min.css" rel="stylesheet" />
                                        <link href="css/styles.css" rel="stylesheet" />
                                        <script src="https://use.fontawesome.com/releases/v6.3.0/js/all.js" crossorigin="anonymous"></script>
                                    </head>
                                    <body class="sb-nav-fixed">
                                        <nav class="sb-topnav navbar navbar-expand navbar-dark bg-dark">
                                            <!-- Navbar Brand-->
                                            <a class="navbar-brand ps-3" href="index.php">GUDANG MANTAF</a>
                                            <!-- Sidebar Toggle-->
                                            <button class="btn btn-link btn-sm order-1 order-lg-0 me-4 me-lg-0" id="sidebarToggle" href="#!"><i class="fas fa-bars"></i></button>
                                            <!-- Navbar Search-->
                                            <form class="d-none d-md-inline-block form-inline ms-auto me-0 me-md-3 my-2 my-md-0">
                                                <div class="input-group">
                                                    <input class="form-control" type="text" placeholder="Search for..." aria-label="Search for..." aria-describedby="btnNavbarSearch" />
                                                    <button class="btn btn-primary" id="btnNavbarSearch" type="button"><i class="fas fa-search"></i></button>
                                                </div>
                                            </form>
                                            
                                        </nav>
                                        <div id="layoutSidenav">
                                            <div id="layoutSidenav_nav">
                                                <nav class="sb-sidenav accordion sb-sidenav-dark" id="sidenavAccordion">
                                                    <div class="sb-sidenav-menu">
                                                        <div class="nav">
                                                            
                                                            <a class="nav-link" href="index.php">
                                                                <div class="sb-nav-link-icon"><i class="fas fa-tachometer-alt"></i></div>
                                                                Stock Barang
                                                            </a>
                                                            <a class="nav-link" href="masuk.php">
                                                                <div class="sb-nav-link-icon"><i class="fas fa-tachometer-alt"></i></div>
                                                                Barang Masuk
                                                            </a>
                                                            <a class="nav-link" href="keluar.php">
                                                                <div class="sb-nav-link-icon"><i class="fas fa-tachometer-alt"></i></div>
                                                                Barang Keluar
                                                            </a>
                                
                                                            <a class="nav-link" href="logout.php">
                                                                <div class="sb-nav-link-icon"><i class="fas fa-tachometer-alt"></i></div>
                                                                Logout
                                                            </a>
                                
                                
                                                        </div>
                                                    </div>
                                                    <div class="sb-sidenav-footer">
                                                        <div class="small">Logged in as:</div>
                                                        Abdul Aziz
                                                    </div>
                                                </nav>
                                            </div>
                                            <div id="layoutSidenav_content">
                                                <main>
                                                    <div class="container-fluid px-4">
                                                        <h1 class="mt-4">Stock Barang</h1>
                                                        
                                                        
                                                        <div class="card mb-4">
                                                            <div class="card-header">
                                
                                
                                                            <button type="button" class="btn btn-primary" data-bs-toggle="modal" data-bs-target="#myModal">
                                                            Tambah Barang
                                                            </button>
                                        
                                                            </div>
                                                            <div class="card-body">
                                                                <div class="table-responsive">
                                                                    <table class="table table-bordered" id="dataTable" width="100%" cellspacing="0">
                                                                    <thead>
                                                                        <tr>
                                                                            <th>No</th>
                                                                            <th>Nama Barang</th>
                                                                            <th>Deskripsi</th>
                                                                            <th>Stock</th>
                                                                      </tr>
                                                                    </thead>
                                                                    <tbody>
                                
                                                                        <?php
                                                                        $ambilsemuadatastock = mysqli_query($conn,"select * from stock");
                                                                        while($data=mysqli_fetch_array($ambilsemuadatastock)){
                                                                            $i = 1;
                                                                            $namabarang = $data['namabarang'];
                                                                            $deskripsi = $data['deskripsi'];
                                                                            $stock = $data['stock'];
                                
                                                                        
                                
                                                                        ?>
                                                                        <tr>
                                                                            <td><?=$i++;?></td>
                                                                            <td><?=$namabarang;?></td>
                                                                            <td><?$deskripsi;?></td>
                                                                            <td><?$stock;?></td>
                                                                        </tr>
                                                                        <?php
                                                                        };
                                
                                                                        ?>
                                
                                                                    </tbody>
                                                                </table>
                                                            </div>
                                                        </div>
                                                    </div>
                                                </main>
                                                <footer class="py-4 bg-light mt-auto">
                                                    <div class="container-fluid px-4">
                                                        <div class="d-flex align-items-center justify-content-between small">
                                                            <div class="text-muted">Copyright &copy; Your Website 2023</div>
                                                            <div>
                                                                <a href="#">Privacy Policy</a>
                                                                &middot;
                                                                <a href="#">Terms &amp; Conditions</a>
                                                            </div>
                                                        </div>
                                                    </div>
                                                </footer>
                                            </div>
                                        </div>
                                        <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.2.3/dist/js/bootstrap.bundle.min.js" crossorigin="anonymous"></script>
                                        <script src="js/scripts.js"></script>
                                        <script src="https://cdnjs.cloudflare.com/ajax/libs/Chart.js/2.8.0/Chart.min.js" crossorigin="anonymous"></script>
                                        <script src="assets/demo/chart-area-demo.js"></script>
                                        <script src="assets/demo/chart-bar-demo.js"></script>
                                        <script src="https://cdn.jsdelivr.net/npm/simple-datatables@7.1.2/dist/umd/simple-datatables.min.js" crossorigin="anonymous"></script>
                                        <script src="js/datatables-simple-demo.js"></script>
                                    </body>
                                
                                    
                                            <!-- The Modal -->
                                     <div class="modal fade" id="myModal">
                                            <div class="modal-dialog">
                                                <div class="modal-content">
                                
                                                <!-- Modal Header -->
                                                <div class="modal-header">
                                                    <h4 class="modal-title">Tambah Barang</h4>
                                                    <button type="button" class="btn-close" data-bs-dismiss="modal"></button>
                                                </div>
                                
                                
                                
                                                <!-- Modal body -->
                                                <form method="post">
                                                <div class="modal-body">
                                                    <input type="text" name="namabarang" placeholder="Nama Barang" class="form-control" required>
                                                    <br>
                                                    <input type="text" name="deskripsi" placeholder="Deskripsi Barang" class="form-control" required>
                                                    <br>
                                                    <input type="number" name="stock"class="form-control" placeholder="Jumlah Barang" required>
                                                    <br>
                                                    <button type="submit" class="btn btn-primary" name="addnewbarang">Submit</button>
                                
                                                </div>
                                                </form>
                                            </div>
                                    </div>
                                    
                                </html>
