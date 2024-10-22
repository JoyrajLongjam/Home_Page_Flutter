//Code
import 'package:flutter/material.dart';

void main() {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Bajaj Auto Credit Limited',

      theme: ThemeData(
        fontFamily: 'Sora',
        primarySwatch: Colors.blue,
      ),
      debugShowCheckedModeBanner: false,
      home: const HomePage(),
    );
  }
}

class HomePage extends StatelessWidget {
  const HomePage({super.key});

  @override

  Widget build(BuildContext context) {
    return Scaffold(
      body: Container(
        width: double.infinity,

        height: double.infinity,
        decoration: const BoxDecoration(
          //////////////////////////////
          image: DecorationImage(
            image: AssetImage('assets/images/za.jpg'),
            fit: BoxFit.cover,
            ///////////////////////////////
          ),
        ),
        child: Padding(
          padding: const EdgeInsets.all(16.0),
          child: Column(
            mainAxisAlignment: MainAxisAlignment.start,
            children: <Widget>[
              //
              Row(
                mainAxisAlignment: MainAxisAlignment.spaceBetween,
                children: [
                  Padding(
                    padding: const EdgeInsets.only(left: 10.0),
                    child: Container(
                      decoration: BoxDecoration(

                        border: Border.all(
                          color: Colors.white.withOpacity(0.3),/////

                          width: 4.0,
                        ),
                        borderRadius: BorderRadius.circular(1.0),
                      ),
                      child: ClipRRect(

                        borderRadius: BorderRadius.circular(1.0),
                        child: Image.asset(
                          ////////////////////////////////
                          'assets/images/qw.png',
                          height: 60,
                          width: 130,
                          ///////////////////////
                          fit: BoxFit.cover,
                        ),
                      ),
                    ),
                  ),
                  Row(

                    children: [
                      buildIconCircle(Icons.volume_off, () {}),
                      ////////////////////////
                      const SizedBox(width: 10),

                      buildIconCircle(Icons.refresh, () {
                        Navigator.pushReplacement(
                          context,
                          PageRouteBuilder(
                            //////////////////////////////
                            pageBuilder: (a, b, c) => const HomePage(),
                            transitionDuration: Duration.zero,
                            ////////////////////
                            reverseTransitionDuration: Duration.zero,
                          ),
                        );
                      }),
                      /////////////////////////
                      const SizedBox(width: 10),
                      buildLanguageButton(),
                      ////////////
                    ],
                  ),
                ],
              ),
              const SizedBox(height: 20),
              ////////////
              const Align(
                alignment: Alignment.centerLeft,
                child: Padding(
                  padding: EdgeInsets.only(left: 8.0),
                  child: Text(
                    'Welcome to the all new',
                    style: TextStyle(
                      color: Colors.white,
                      fontSize: 25,
                      fontWeight: FontWeight.bold,
                    ),
                  ),
                ),
              ),
              const SizedBox(height: 5),
              const Align(

                alignment: Alignment.centerLeft,
                child: Padding(
                  padding: EdgeInsets.only(left: 8.0),
                  child: Text(
                    'BAJAJ AUTO CREDIT LIMITED',
                    style: TextStyle(
                      color: Colors.white,
                      fontSize: 45,
                      fontWeight: FontWeight.bold,
                    ),
                  ),
                ),

              ),
              const SizedBox(height: 20),
              Expanded(
                //////////////////////////
                child: SingleChildScrollView(
                  scrollDirection: Axis.horizontal,
                  child: Row(
                    crossAxisAlignment: CrossAxisAlignment.start,
                    children: <Widget>[
                      buildOptionCard(
                        context,
                        /////////////////////////////////
                        image: 'assets/images/bank.png',
                        title: 'Finance my dream bike',
                        description: 'A two wheeler loan enables you to buy a bike of your choice',
                        backgroundColor: const Color(0xFF2979FF),
                        textColor: Colors.white,
                        /////////////////////////////////
                        onTap: () {},
                      ),
                      const SizedBox(width: 24),
                      buildOptionCard(
                        context,
                        image: 'assets/images/cash.png',
                        title: 'Pay EMI',
                        description: 'Pay loan EMI with Bajaj Quick Pay made it easy',
                        backgroundColor: const Color(0xFF2196F3),
                        textColor: Colors.white,
                        onTap: () {},
                        //////////////////////////////
                      ),
                      const SizedBox(width: 24),
                      buildOptionCard(
                        context,
                        image: 'assets/images/bike.png',
                        title: 'Explore Bikes',
                        ///////////////////////
                        description: 'Introducing the All-New range of Bajaj Models',
                        backgroundColor: const Color(0xFF4CAF50),
                        textColor: Colors.white,
                        /////////////////////
                        onTap: () {},
                      ),
                      const SizedBox(width: 24),
                      buildOptionCard(
                        context,
                        image: 'assets/images/support.png',
                        title: 'Customer Service',
                        description: 'The support and assistance a company offers...',
                        backgroundColor: const Color(0xFFF44336),
                        textColor: Colors.white,
                        onTap: () {},
                        //////////
                      ),
                    ],
                  ),
                ),
              ),
              const Text(
                '© 2024 Bajaj Auto Credit Ltd. All Rights Reserved.',
                style: TextStyle(
                  color: Colors.white,
                  fontSize: 12,
                  fontWeight: FontWeight.w400,
                ),
                textAlign: TextAlign.center,
              ),
            ],
          ),
        ),
      ),
    );
  }

  Widget buildIconCircle(IconData icon, VoidCallback onPressed) {
    return Container(
      decoration: BoxDecoration(
        shape: BoxShape.circle,
        color: Colors.white.withOpacity(0.3),
      ),
      ////////////////////////
      width: 48,
      height: 48,
      ///////////////////////
      child: IconButton(
        icon: Icon(icon, color: Colors.white),
        onPressed: onPressed,
      ),
    );
  }

  Widget buildLanguageButton() {
    return Container(
      decoration: BoxDecoration(
        color: Colors.white.withOpacity(0.3),
        borderRadius: BorderRadius.circular(30.0),
      ),
      padding: const EdgeInsets.symmetric(horizontal: 12.0, vertical: 6.0),
      ////////////////////
      child: ElevatedButton.icon(
        onPressed: () {},
        icon: const Icon(Icons.language, color: Colors.white),
        label: Row(
          ////////////////////
          children: [
            const Text('English', style: TextStyle(color: Colors.white)),
            const SizedBox(width: 8),
            const Text(
              '>',
              style: TextStyle(
                color: Colors.white,
                fontWeight: FontWeight.bold,
                fontSize: 16,
              ),
            ),
          ],
        ),
        style: ElevatedButton.styleFrom(
          backgroundColor: Colors.transparent,
          shadowColor: Colors.transparent,
        ),
      ),
    );
  }

  Widget buildOptionCard(BuildContext context,
      {required String image,
        required String title,
        /////////////////
        required String description,
        required Color backgroundColor,
        required Color textColor,

        required VoidCallback onTap}) {
    return GestureDetector(
      onTap: onTap,
      child: SizedBox(
        width: MediaQuery.of(context).size.width / 4.5,
        height: MediaQuery.of(context).size.height / 1.1,
        child: Card(
          shape: RoundedRectangleBorder(
            borderRadius: BorderRadius.circular(16.0),
          ),
          ////////////////////////
          elevation: 10.0,
          child: Container(
            decoration: BoxDecoration(
              gradient: LinearGradient(
                colors: [backgroundColor, backgroundColor.withOpacity(0.8)],
                begin: Alignment.topLeft,
                end: Alignment.bottomRight,
              ),
              borderRadius: BorderRadius.circular(16.0),
              boxShadow: [
                BoxShadow(
                  color: Colors.black.withOpacity(0.8),
                  offset: Offset(4, 4),
                  blurRadius: 10.0,
                ),
              ],
            ),
            child: Stack(
              clipBehavior: Clip.none,
              children: <Widget>[
                Positioned(
                  top: -70,
                  left: MediaQuery.of(context).size.width / 35,
                  child: Padding(
                    padding: const EdgeInsets.all(10.0),
                    child: Image.asset(
                      image,
                      fit: BoxFit.contain,
                      height: 180,
                      width: 180,
                    ),
                  ),
                ),
                Padding(
                  ////////////////////
                  padding: const EdgeInsets.only(top: 70.0),
                  child: Column(
                    mainAxisAlignment: MainAxisAlignment.center,
                    children: <Widget>[
                      //////////////////////////
                      const SizedBox(height: 1.0),
                      Text(
                        title,
                        style: TextStyle(
                          fontSize: 22,
                          fontWeight: FontWeight.bold,
                          color: textColor,
                          shadows: [
                            Shadow(
                              color: Colors.black.withOpacity(1),
                              offset: const Offset(3, 3),
                              blurRadius: 6,
                            ),
                          ],
                        ),
                        textAlign: TextAlign.center,
                      ),
                      const SizedBox(height: 10.0),
                      Text(
                        description,
                        style: TextStyle(fontSize: 15, color: textColor),
                        textAlign: TextAlign.center,
                      ),
                    ],
                  ),
                ),
                ////////////////////////////////
                Positioned(
                  bottom: 8.0,
                  right: 8.0,
                  child: const Icon(
                    ////////////////////////////
                    Icons.arrow_forward,
                    color: Colors.white,
                    size: 26,
                  ),
                  
                ),
              ],

            ),
          ),

        ),
      ),

    );
  }

}

