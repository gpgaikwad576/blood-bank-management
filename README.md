# blood-bank-management
-- phpMyAdmin SQL Dump
-- version 4.9.5
-- https://www.phpmyadmin.net/
--
-- Host: localhost:8889
-- Generation Time: Feb 17, 2021 at 02:34 PM
-- Server version: 5.7.24
-- PHP Version: 7.4.1

SET SQL_MODE = "NO_AUTO_VALUE_ON_ZERO";
SET AUTOCOMMIT = 0;
START TRANSACTION;
SET time_zone = "+00:00";


/*!40101 SET @OLD_CHARACTER_SET_CLIENT=@@CHARACTER_SET_CLIENT */;
/*!40101 SET @OLD_CHARACTER_SET_RESULTS=@@CHARACTER_SET_RESULTS */;
/*!40101 SET @OLD_COLLATION_CONNECTION=@@COLLATION_CONNECTION */;
/*!40101 SET NAMES utf8mb4 */;

--
-- Database: `blood`
--
CREATE DATABASE IF NOT EXISTS `blood` DEFAULT CHARACTER SET utf8 COLLATE utf8_general_ci;
USE `blood`;

-- --------------------------------------------------------

--
-- Table structure for table `blood`
--

CREATE TABLE `blood` (
  `bid` int(11) NOT NULL,
  `did` int(11) NOT NULL,
  `eid` int(11) NOT NULL,
  `bamount` int(11) NOT NULL,
  `bgroup` varchar(5) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8;

--
-- Dumping data for table `blood`
--

INSERT INTO `blood` (`bid`, `did`, `eid`, `bamount`, `bgroup`) VALUES
(1001, 100, 901, 2, 'A+'),
(1002, 102, 902, 1, 'A+'),
(1003, 100, 903, 1, 'A+'),
(1004, 104, 903, 2, 'B+'),
(1005, 104, 902, 1, 'B+'),
(1006, 108, 903, 1, 'A-'),
(1007, 105, 904, 1, 'AB+'),
(1008, 105, 901, 1, 'AB+'),
(1009, 107, 904, 2, 'AB-'),
(1010, 106, 905, 1, 'AB-'),
(1011, 103, 901, 1, 'O+'),
(1012, 103, 904, 2, 'O+'),
(1013, 101, 905, 2, 'O-'),
(1014, 101, 901, 2, 'O-'),
(1015, 109, 905, 1, 'B-'),
(1016, 109, 902, 1, 'B-'),
(1017, 102, 905, 2, 'A+'),
(1018, 100, 901, 5, 'B+'),
(1019, 100, 901, 3, 'AB+'),
(1020, 100, 902, 4, 'A+'),
(2021, 100, 902, 4, 'O+'),
(2023, 100, 901, 4, 'O+'),
(5467, 100, 903, 89, 'O+'),
(5567, 100, 903, 89, 'O+'),
(8567, 100, 903, 89, 'O+'),
(8967, 100, 903, 89, 'O+'),
(9567, 100, 903, 89, 'O+'),
(9967, 100, 903, 89, 'O+');

-- --------------------------------------------------------

--
-- Stand-in structure for view `bloodeachcollector`
-- (See below for the actual view)
--
CREATE TABLE `bloodeachcollector` (
`eid` int(11)
,`Blood_collected` decimal(32,0)
);

-- --------------------------------------------------------

--
-- Table structure for table `collecteby`
--

CREATE TABLE `collecteby` (
  `eid` int(11) DEFAULT NULL,
  `bid` int(11) DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8;

--
-- Dumping data for table `collecteby`
--

INSERT INTO `collecteby` (`eid`, `bid`) VALUES
(901, 1001),
(902, 1002),
(903, 1003),
(903, 1004),
(902, 1005),
(903, 1006),
(904, 1007),
(901, 1008),
(904, 1009),
(905, 1010),
(901, 1011),
(904, 1012),
(905, 1013),
(901, 1014),
(905, 1015),
(902, 1016),
(905, 1017),
(901, 1001),
(902, 1002),
(903, 1003),
(903, 1004),
(902, 1005),
(903, 1006),
(904, 1007),
(901, 1008),
(904, 1009),
(905, 1010),
(901, 1011),
(904, 1012),
(905, 1013),
(901, 1014),
(905, 1015),
(902, 1016),
(905, 1017);

-- --------------------------------------------------------

--
-- Table structure for table `collector`
--

CREATE TABLE `collector` (
  `eid` int(11) DEFAULT NULL,
  `workexperience` int(11) DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8;

--
-- Dumping data for table `collector`
--

INSERT INTO `collector` (`eid`, `workexperience`) VALUES
(900, 24),
(901, 567),
(902, 14),
(903, 4),
(904, 20),
(905, 29),
(906, 17);

-- --------------------------------------------------------

--
-- Table structure for table `donates`
--

CREATE TABLE `donates` (
  `did` int(11) DEFAULT NULL,
  `bid` int(11) DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8;

--
-- Dumping data for table `donates`
--

INSERT INTO `donates` (`did`, `bid`) VALUES
(100, 1001),
(102, 1002),
(100, 1003),
(104, 1004),
(104, 1005),
(108, 1006),
(105, 1007),
(105, 1008),
(107, 1009),
(106, 1010),
(103, 1011),
(103, 1012),
(101, 1013),
(101, 1014),
(109, 1015),
(109, 1016),
(102, 1017),
(100, 1001),
(102, 1002),
(100, 1003),
(104, 1004),
(104, 1005),
(108, 1006),
(105, 1007),
(105, 1008),
(107, 1009),
(106, 1010),
(103, 1011),
(103, 1012),
(101, 1013),
(101, 1014),
(109, 1015),
(109, 1016),
(102, 1017);

-- --------------------------------------------------------

--
-- Table structure for table `donors`
--

CREATE TABLE `donors` (
  `did` int(11) NOT NULL,
  `dname` varchar(50) NOT NULL,
  `address` varchar(255) DEFAULT NULL,
  `age` int(11) NOT NULL,
  `gender` varchar(50) DEFAULT NULL,
  `lastdate` date DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8;

--
-- Dumping data for table `donors`
--

INSERT INTO `donors` (`did`, `dname`, `address`, `age`, `gender`, `lastdate`) VALUES
(100, 'Kunal Kadam', 'Checknaka, Thane - 4', 18, 'Male', '2020-10-02'),
(101, 'Pankaj Gaikwad', 'Vaishali Nagar, Mulund', 19, 'Male', '2020-10-02'),
(102, 'Priya Deshmukh', 'Golden Park, Kurla ', 21, 'Female', '2020-10-02'),
(103, 'Kanchana Kadam', 'Hiramoti nagar, Thane - 4', 18, 'Female', '2020-10-02'),
(104, 'Gargi Patil', 'Vitthal Nagar, Mulund', 18, 'Female', '2020-10-02'),
(105, 'Rahul Pandey', 'MG road, Mumbai', 18, 'Male', '2020-10-02'),
(106, 'Manoj Kumar', 'Vaishali Nagar, Mulund', 21, 'Male', '2020-10-05'),
(107, 'Rohit Shing', 'Golden Park, Kurla', 18, 'Male', '2020-10-05'),
(108, 'Pranjal Nikam', 'Checknaka, Thane - 4', 20, 'Female', '2020-10-05'),
(109, 'Kiran Shinde', 'Vitthal Nagar, Mulund', 18, 'Female', '2020-10-05'),
(110, 'ravi shankar', 'delhi', 18, 'male', '2020-10-23');

--
-- Triggers `donors`
--
DELIMITER $$
CREATE TRIGGER `donors_age` BEFORE INSERT ON `donors` FOR EACH ROW if new.age<18 or new.age>60 THEN signal sqlstate '20000' set message_text='People below age 18 can not donate'; end if
$$
DELIMITER ;
DELIMITER $$
CREATE TRIGGER `donors_date` BEFORE INSERT ON `donors` FOR EACH ROW if new.lastdate<now()
then signal sqlstate '20000' set message_text='date is before today!';
end if
$$
DELIMITER ;

-- --------------------------------------------------------

--
-- Table structure for table `donor_conc`
--

CREATE TABLE `donor_conc` (
  `did` int(11) DEFAULT NULL,
  `contactno` int(11) DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8;

--
-- Dumping data for table `donor_conc`
--

INSERT INTO `donor_conc` (`did`, `contactno`) VALUES
(100, 987766546),
(102, 887677654),
(103, 899765597),
(105, 978906066),
(105, 988797979),
(107, 979080777),
(109, 876968900),
(109, 987766546);

--
-- Triggers `donor_conc`
--
DELIMITER $$
CREATE TRIGGER `donor_conc_contactno` BEFORE INSERT ON `donor_conc` FOR EACH ROW if new.contactno>999999999 or new.contactno<000000000
then signal sqlstate '20002' set message_text='Contact number is not valid';
end if
$$
DELIMITER ;

-- --------------------------------------------------------

--
-- Stand-in structure for view `eligibledonor`
-- (See below for the actual view)
--
CREATE TABLE `eligibledonor` (
`did` int(11)
,`dname` varchar(50)
,`contactno` int(11)
);

-- --------------------------------------------------------

--
-- Table structure for table `employee`
--

CREATE TABLE `employee` (
  `eid` int(11) NOT NULL,
  `ename` varchar(50) NOT NULL,
  `address` varchar(255) DEFAULT NULL,
  `salary` decimal(7,2) NOT NULL,
  `joiningdate` date NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8;

--
-- Dumping data for table `employee`
--

INSERT INTO `employee` (`eid`, `ename`, `address`, `salary`, `joiningdate`) VALUES
(900, 'Lalit Rao', 'Checknaka, Thane - 4', '3500.00', '2018-04-30'),
(901, 'Dinesh Verma', 'Checknaka, Thane - 4', '5000.00', '2015-10-21'),
(902, 'Sahil Sawant', 'Vitthal Nagar, Mulund', '6000.00', '2015-11-22'),
(903, 'Krish Karma', 'MG road, Mumbai', '6000.00', '2016-03-04'),
(904, 'Mrunal Panchal', 'Checknaka, Thane - 4', '6500.00', '2013-04-23'),
(905, 'Dikshir Dhanu', 'MG road, Mumbai', '5400.00', '2014-06-21'),
(906, 'Pratik Shetty', 'MG road, Mumbai', '7000.00', '2015-02-19'),
(907, 'Aadarsh Puri', 'Hiramoti nagar, Thane - 4', '6000.00', '2016-02-09'),
(908, 'Suraj Kumar', 'MG road, Mumbai', '7000.00', '2011-09-12'),
(909, 'Uma Kore', 'Vitthal Nagar, Mulund', '7400.00', '2016-01-01');

-- --------------------------------------------------------

--
-- Table structure for table `employee_conc`
--

CREATE TABLE `employee_conc` (
  `eid` int(11) DEFAULT NULL,
  `contactno` int(11) DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8;

--
-- Dumping data for table `employee_conc`
--

INSERT INTO `employee_conc` (`eid`, `contactno`) VALUES
(901, 988798079),
(902, 989079797),
(903, 989807970),
(904, 989080807),
(905, 977077009),
(903, 989897070),
(905, 989807077),
(906, 987070799),
(907, 999897979),
(908, 799788764);

--
-- Triggers `employee_conc`
--
DELIMITER $$
CREATE TRIGGER `employee_conc_contactno` BEFORE INSERT ON `employee_conc` FOR EACH ROW if new.contactno>999999999 or new.contactno<000000000
then signal sqlstate '20002' set message_text='Contact number is not valid';
end if
$$
DELIMITER ;

-- --------------------------------------------------------

--
-- Stand-in structure for view `groupwisedonor`
-- (See below for the actual view)
--
CREATE TABLE `groupwisedonor` (
`did` int(11)
,`dname` varchar(50)
,`contactno` int(11)
);

-- --------------------------------------------------------

--
-- Stand-in structure for view `groupwisenodonors`
-- (See below for the actual view)
--
CREATE TABLE `groupwisenodonors` (
`bgroup` varchar(5)
,`no_of_Donors` bigint(21)
);

-- --------------------------------------------------------

--
-- Table structure for table `hospital`
--

CREATE TABLE `hospital` (
  `hid` int(11) NOT NULL,
  `hname` varchar(50) NOT NULL,
  `address` varchar(255) DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8;

--
-- Dumping data for table `hospital`
--

INSERT INTO `hospital` (`hid`, `hname`, `address`) VALUES
(501, 'Mumbai Hospital', 'bharat road,kanjurmarg,mumbai'),
(502, 'City Hospital', 'Mg Road, Dadar, Mumbai'),
(503, 'Jupiter Hospital', 'Grant Road, Kanjurmarg, Mumbai'),
(504, 'Star Hospital', 'Kissan nagar - 2, Bhatwadi, Thane'),
(505, 'Save Life Hospital', 'VijayaLaxmi nagar, Bhandup, Mumbai'),
(506, 'Thane Hospital', 'Shivaji nagar, Thane');

-- --------------------------------------------------------

--
-- Table structure for table `hospital_conc`
--

CREATE TABLE `hospital_conc` (
  `hid` int(11) DEFAULT NULL,
  `telephoneno` int(11) DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8;

--
-- Dumping data for table `hospital_conc`
--

INSERT INTO `hospital_conc` (`hid`, `telephoneno`) VALUES
(501, 898769765),
(502, 987989798),
(503, 898769765),
(504, 768970706),
(505, 898769765),
(503, 887660986),
(505, 867686976),
(506, 889799698);

--
-- Triggers `hospital_conc`
--
DELIMITER $$
CREATE TRIGGER `hospital_conc_telephoneno` BEFORE INSERT ON `hospital_conc` FOR EACH ROW if new.telephoneno>999999999 or new.telephoneno<000000000
then signal sqlstate '20002' set message_text='Contact number is not valid';
end if
$$
DELIMITER ;

-- --------------------------------------------------------

--
-- Table structure for table `logs`
--

CREATE TABLE `logs` (
  `table_name` varchar(30) DEFAULT NULL,
  `action` varchar(30) DEFAULT NULL,
  `time` timestamp NOT NULL DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP
) ENGINE=InnoDB DEFAULT CHARSET=utf8;

--
-- Dumping data for table `logs`
--

INSERT INTO `logs` (`table_name`, `action`, `time`) VALUES
('donors', 'address inserted', '2020-10-22 12:32:29'),
('hospital', 'address changed', '2020-10-22 14:25:38');

-- --------------------------------------------------------

--
-- Table structure for table `receptionist`
--

CREATE TABLE `receptionist` (
  `eid` int(11) DEFAULT NULL,
  `dcount` int(11) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8;

--
-- Dumping data for table `receptionist`
--

INSERT INTO `receptionist` (`eid`, `dcount`) VALUES
(907, 4),
(908, 14),
(909, 24);

--
-- Triggers `receptionist`
--
DELIMITER $$
CREATE TRIGGER `receptionist_after_delete` AFTER DELETE ON `receptionist` FOR EACH ROW delete from employee where employee.eid=receptionist.eid
$$
DELIMITER ;

-- --------------------------------------------------------

--
-- Table structure for table `soldto`
--

CREATE TABLE `soldto` (
  `bid` int(11) NOT NULL,
  `hid` int(11) NOT NULL,
  `transdate` date DEFAULT NULL,
  `bcost` decimal(7,2) NOT NULL,
  `fax` varchar(250) DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8;

--
-- Dumping data for table `soldto`
--

INSERT INTO `soldto` (`bid`, `hid`, `transdate`, `bcost`, `fax`) VALUES
(1001, 501, '2020-09-15', '2000.00', 'Transaction of 2 liters of A+ Blood'),
(1002, 501, '2020-10-11', '1000.00', 'Transaction of 1 liters of A+ Blood'),
(1003, 502, '2020-08-15', '2000.00', 'Transaction of 1 liters of A+ Blood'),
(1004, 502, '2020-07-14', '3000.00', 'Transaction of 2 liters of B+ Blood'),
(1005, 503, '2020-08-17', '3000.00', 'Transaction of 1 liters of B+ Blood'),
(1006, 504, '2020-09-15', '2000.00', 'Transaction of 1 liters of A- Blood');

-- --------------------------------------------------------

--
-- Stand-in structure for view `totalblood`
-- (See below for the actual view)
--
CREATE TABLE `totalblood` (
`bgroup` varchar(5)
,`Blood_Amount` decimal(32,0)
);

-- --------------------------------------------------------

--
-- Stand-in structure for view `transhos`
-- (See below for the actual view)
--
CREATE TABLE `transhos` (
`Hid` int(11)
,`Hname` varchar(50)
,`transdate` date
,`fax` varchar(250)
);

-- --------------------------------------------------------

--
-- Structure for view `bloodeachcollector`
--
DROP TABLE IF EXISTS `bloodeachcollector`;

CREATE ALGORITHM=UNDEFINED DEFINER=`root`@`localhost` SQL SECURITY DEFINER VIEW `bloodeachcollector`  AS  select `collector`.`eid` AS `eid`,sum(`bamount`) AS `Blood_collected` from (`blood` join `collector` on((`eid` = `collector`.`eid`))) group by `collector`.`eid` ;

-- --------------------------------------------------------

--
-- Structure for view `eligibledonor`
--
DROP TABLE IF EXISTS `eligibledonor`;

CREATE ALGORITHM=UNDEFINED DEFINER=`root`@`localhost` SQL SECURITY DEFINER VIEW `eligibledonor`  AS  select `donors`.`did` AS `did`,`donors`.`dname` AS `dname`,`donor_conc`.`contactno` AS `contactno` from (`donors` join `donor_conc`) where ((timestampdiff(MONTH,now(),`donors`.`lastdate`) >= 6) and (`donor_conc`.`did` = `donors`.`did`)) ;

-- --------------------------------------------------------

--
-- Structure for view `groupwisedonor`
--
DROP TABLE IF EXISTS `groupwisedonor`;

CREATE ALGORITHM=UNDEFINED DEFINER=`root`@`localhost` SQL SECURITY DEFINER VIEW `groupwisedonor`  AS  select distinct `d`.`did` AS `did`,`d`.`dname` AS `dname`,`dc`.`contactno` AS `contactno` from ((`donors` `d` join `donor_conc` `dc` on((`d`.`did` = `dc`.`did`))) join `blood` `b` on(((`d`.`did` = `b`.`did`) and (`b`.`bgroup` = 'A+')))) ;

-- --------------------------------------------------------

--
-- Structure for view `groupwisenodonors`
--
DROP TABLE IF EXISTS `groupwisenodonors`;

CREATE ALGORITHM=UNDEFINED DEFINER=`root`@`localhost` SQL SECURITY DEFINER VIEW `groupwisenodonors`  AS  select `bgroup` AS `bgroup`,count(0) AS `no_of_Donors` from `blood` group by `bgroup` ;

-- --------------------------------------------------------

--
-- Structure for view `totalblood`
--
DROP TABLE IF EXISTS `totalblood`;

CREATE ALGORITHM=UNDEFINED DEFINER=`root`@`localhost` SQL SECURITY DEFINER VIEW `totalblood`  AS  select `bgroup` AS `bgroup`,sum(`bamount`) AS `Blood_Amount` from `blood` group by `bgroup` ;

-- --------------------------------------------------------

--
-- Structure for view `transhos`
--
DROP TABLE IF EXISTS `transhos`;

CREATE ALGORITHM=UNDEFINED DEFINER=`root`@`localhost` SQL SECURITY DEFINER VIEW `transhos`  AS  select `hospital`.`hid` AS `Hid`,`hospital`.`hname` AS `Hname`,`soldto`.`transdate` AS `transdate`,`soldto`.`fax` AS `fax` from (`hospital` join `soldto`) where ((`hospital`.`hid` = `soldto`.`hid`) and (`hospital`.`hid` = 502)) ;

--
-- Indexes for dumped tables
--

--
-- Indexes for table `blood`
--
ALTER TABLE `blood`
  ADD PRIMARY KEY (`bid`),
  ADD KEY `did` (`did`),
  ADD KEY `eid` (`eid`);

--
-- Indexes for table `collecteby`
--
ALTER TABLE `collecteby`
  ADD KEY `eid` (`eid`),
  ADD KEY `bid` (`bid`);

--
-- Indexes for table `collector`
--
ALTER TABLE `collector`
  ADD KEY `eid` (`eid`);

--
-- Indexes for table `donates`
--
ALTER TABLE `donates`
  ADD KEY `did` (`did`),
  ADD KEY `bid` (`bid`);

--
-- Indexes for table `donors`
--
ALTER TABLE `donors`
  ADD PRIMARY KEY (`did`);

--
-- Indexes for table `donor_conc`
--
ALTER TABLE `donor_conc`
  ADD KEY `did` (`did`);

--
-- Indexes for table `employee`
--
ALTER TABLE `employee`
  ADD PRIMARY KEY (`eid`);

--
-- Indexes for table `employee_conc`
--
ALTER TABLE `employee_conc`
  ADD KEY `eid` (`eid`);

--
-- Indexes for table `hospital`
--
ALTER TABLE `hospital`
  ADD PRIMARY KEY (`hid`);

--
-- Indexes for table `hospital_conc`
--
ALTER TABLE `hospital_conc`
  ADD KEY `hid` (`hid`);

--
-- Indexes for table `receptionist`
--
ALTER TABLE `receptionist`
  ADD KEY `eid` (`eid`);

--
-- Indexes for table `soldto`
--
ALTER TABLE `soldto`
  ADD KEY `bid` (`bid`),
  ADD KEY `hid` (`hid`);

--
-- Constraints for dumped tables
--

--
-- Constraints for table `blood`
--
ALTER TABLE `blood`
  ADD CONSTRAINT `blood_ibfk_1` FOREIGN KEY (`did`) REFERENCES `donors` (`did`),
  ADD CONSTRAINT `blood_ibfk_2` FOREIGN KEY (`eid`) REFERENCES `employee` (`eid`);

--
-- Constraints for table `collecteby`
--
ALTER TABLE `collecteby`
  ADD CONSTRAINT `collecteby_ibfk_1` FOREIGN KEY (`eid`) REFERENCES `employee` (`eid`),
  ADD CONSTRAINT `collecteby_ibfk_2` FOREIGN KEY (`bid`) REFERENCES `blood` (`bid`);

--
-- Constraints for table `collector`
--
ALTER TABLE `collector`
  ADD CONSTRAINT `collector_ibfk_1` FOREIGN KEY (`eid`) REFERENCES `employee` (`eid`);

--
-- Constraints for table `donates`
--
ALTER TABLE `donates`
  ADD CONSTRAINT `donates_ibfk_1` FOREIGN KEY (`did`) REFERENCES `donors` (`did`),
  ADD CONSTRAINT `donates_ibfk_2` FOREIGN KEY (`bid`) REFERENCES `blood` (`bid`);

--
-- Constraints for table `donor_conc`
--
ALTER TABLE `donor_conc`
  ADD CONSTRAINT `donor_conc_ibfk_1` FOREIGN KEY (`did`) REFERENCES `donors` (`did`);

--
-- Constraints for table `employee_conc`
--
ALTER TABLE `employee_conc`
  ADD CONSTRAINT `employee_conc_ibfk_1` FOREIGN KEY (`eid`) REFERENCES `employee` (`eid`);

--
-- Constraints for table `hospital_conc`
--
ALTER TABLE `hospital_conc`
  ADD CONSTRAINT `hospital_conc_ibfk_1` FOREIGN KEY (`hid`) REFERENCES `hospital` (`hid`);

--
-- Constraints for table `receptionist`
--
ALTER TABLE `receptionist`
  ADD CONSTRAINT `receptionist_ibfk_1` FOREIGN KEY (`eid`) REFERENCES `employee` (`eid`);

--
-- Constraints for table `soldto`
--
ALTER TABLE `soldto`
  ADD CONSTRAINT `soldto_ibfk_1` FOREIGN KEY (`bid`) REFERENCES `blood` (`bid`),
  ADD CONSTRAINT `soldto_ibfk_2` FOREIGN KEY (`hid`) REFERENCES `hospital` (`hid`);
--
-- Database: `music`
--
CREATE DATABASE IF NOT EXISTS `music` DEFAULT CHARACTER SET utf8 COLLATE utf8_general_ci;
USE `music`;

-- --------------------------------------------------------

--
-- Table structure for table `albums`
--

CREATE TABLE `albums` (
  `album_id` int(11) NOT NULL,
  `name` varchar(128) DEFAULT NULL,
  `artist_id` int(11) DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8;

--
-- Dumping data for table `albums`
--

INSERT INTO `albums` (`album_id`, `name`, `artist_id`) VALUES
(1, 'chala hawa yeu dya', 1),
(2, 'zing zing zingat', 1),
(3, 'tiranga', 1),
(4, 'lal lipstick', 2),
(5, 'mukhda vekh ke', 3);

-- --------------------------------------------------------

--
-- Table structure for table `artists`
--

CREATE TABLE `artists` (
  `artist_id` int(11) NOT NULL,
  `name` varchar(128) DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8;

--
-- Dumping data for table `artists`
--

INSERT INTO `artists` (`artist_id`, `name`) VALUES
(3, 'ajay'),
(1, 'pankaj'),
(2, 'ravi');

-- --------------------------------------------------------

--
-- Table structure for table `genres`
--

CREATE TABLE `genres` (
  `genre_id` int(11) NOT NULL,
  `name` varchar(128) DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8;

--
-- Dumping data for table `genres`
--

INSERT INTO `genres` (`genre_id`, `name`) VALUES
(2, 'jazz'),
(1, 'rock');

-- --------------------------------------------------------

--
-- Table structure for table `monors`
--

CREATE TABLE `monors` (
  `age` int(11) DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8;

-- --------------------------------------------------------

--
-- Table structure for table `tracks`
--

CREATE TABLE `tracks` (
  `track_id` int(11) NOT NULL,
  `name` varchar(128) DEFAULT NULL,
  `len` int(11) DEFAULT NULL,
  `count` int(11) DEFAULT NULL,
  `rating` int(11) DEFAULT NULL,
  `album_id` int(11) DEFAULT NULL,
  `genre_id` int(11) DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8;

--
-- Dumping data for table `tracks`
--

INSERT INTO `tracks` (`track_id`, `name`, `len`, `count`, `rating`, `album_id`, `genre_id`) VALUES
(1, 'lutiya', 5, 5, 5, 1, 1),
(2, 'chitiya', 5, 5, 5, 1, 1),
(3, 'aankh marey', 5, 5, 5, 1, 1),
(4, 'dil kamjor', 5, 5, 5, 1, 1),
(5, 'aaling dala', 5, 5, 5, 2, 1),
(6, 'sairat zal ji', 5, 5, 5, 2, 1),
(7, 'zing zing zingat', 5, 5, 5, 2, 1),
(8, 'atach baya', 5, 5, 5, 2, 1),
(9, 'balumama', 5, 5, 5, 3, 1),
(10, 'jay deva ', 5, 5, 5, 3, 1),
(11, 'ganpatichi aarti', 5, 5, 5, 3, 1),
(12, 'mera saiya saiko', 5, 5, 5, 3, 1),
(13, 'bahubali big boss', 5, 5, 5, 3, 1),
(14, 'boss maruti', 5, 5, 5, 4, 1),
(15, 'jab koi bat bigad jaye', 5, 5, 5, 4, 1),
(16, 'na na karke pyaar', 5, 5, 5, 4, 1),
(17, 'shivaji maharaj ki jay', 5, 5, 5, 4, 2),
(18, 'kanada raja pandharicha', 5, 5, 5, 4, 2),
(19, 'banu baya', 5, 5, 5, 5, 2),
(20, 'tarzon', 5, 5, 5, 5, 2);

--
-- Indexes for dumped tables
--

--
-- Indexes for table `albums`
--
ALTER TABLE `albums`
  ADD PRIMARY KEY (`album_id`),
  ADD KEY `name` (`name`),
  ADD KEY `artist_id` (`artist_id`);

--
-- Indexes for table `artists`
--
ALTER TABLE `artists`
  ADD PRIMARY KEY (`artist_id`),
  ADD KEY `name` (`name`);

--
-- Indexes for table `genres`
--
ALTER TABLE `genres`
  ADD PRIMARY KEY (`genre_id`),
  ADD KEY `name` (`name`);

--
-- Indexes for table `tracks`
--
ALTER TABLE `tracks`
  ADD PRIMARY KEY (`track_id`),
  ADD KEY `name` (`name`),
  ADD KEY `album_id` (`album_id`),
  ADD KEY `genre_id` (`genre_id`);

--
-- AUTO_INCREMENT for dumped tables
--

--
-- AUTO_INCREMENT for table `albums`
--
ALTER TABLE `albums`
  MODIFY `album_id` int(11) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=6;

--
-- AUTO_INCREMENT for table `artists`
--
ALTER TABLE `artists`
  MODIFY `artist_id` int(11) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=4;

--
-- AUTO_INCREMENT for table `genres`
--
ALTER TABLE `genres`
  MODIFY `genre_id` int(11) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=3;

--
-- AUTO_INCREMENT for table `tracks`
--
ALTER TABLE `tracks`
  MODIFY `track_id` int(11) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=21;

--
-- Constraints for dumped tables
--

--
-- Constraints for table `albums`
--
ALTER TABLE `albums`
  ADD CONSTRAINT `albums_ibfk_1` FOREIGN KEY (`artist_id`) REFERENCES `artists` (`artist_id`) ON DELETE CASCADE ON UPDATE CASCADE;

--
-- Constraints for table `tracks`
--
ALTER TABLE `tracks`
  ADD CONSTRAINT `tracks_ibfk_1` FOREIGN KEY (`album_id`) REFERENCES `albums` (`album_id`) ON DELETE CASCADE ON UPDATE CASCADE,
  ADD CONSTRAINT `tracks_ibfk_2` FOREIGN KEY (`genre_id`) REFERENCES `genres` (`genre_id`) ON DELETE CASCADE ON UPDATE CASCADE;
--
-- Database: `plsqlpankaj`
--
CREATE DATABASE IF NOT EXISTS `plsqlpankaj` DEFAULT CHARACTER SET utf8 COLLATE utf8_general_ci;
USE `plsqlpankaj`;
--
-- Database: `roster`
--
CREATE DATABASE IF NOT EXISTS `roster` DEFAULT CHARACTER SET utf8 COLLATE utf8_general_ci;
USE `roster`;

-- --------------------------------------------------------

--
-- Table structure for table `course`
--

CREATE TABLE `course` (
  `course_id` int(11) NOT NULL,
  `title` varchar(128) DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8;

--
-- Dumping data for table `course`
--

INSERT INTO `course` (`course_id`, `title`) VALUES
(1, 'si106'),
(2, 'si110'),
(3, 'si206');

-- --------------------------------------------------------

--
-- Table structure for table `member`
--

CREATE TABLE `member` (
  `user_id` int(11) NOT NULL,
  `course_id` int(11) NOT NULL,
  `role` int(11) DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8;

--
-- Dumping data for table `member`
--

INSERT INTO `member` (`user_id`, `course_id`, `role`) VALUES
(1, 1, 1),
(2, 1, 0),
(3, 1, 0),
(4, 1, 0),
(5, 1, 0),
(6, 2, 1),
(7, 2, 0),
(8, 2, 0),
(9, 2, 0),
(10, 2, 0),
(11, 3, 1),
(12, 3, 0),
(13, 3, 0),
(14, 3, 0),
(15, 3, 0);

-- --------------------------------------------------------

--
-- Table structure for table `user`
--

CREATE TABLE `user` (
  `user_id` int(11) NOT NULL,
  `name` varchar(128) DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8;

--
-- Dumping data for table `user`
--

INSERT INTO `user` (`user_id`, `name`) VALUES
(1, 'Alieu'),
(2, 'Amarah'),
(3, 'Cacie'),
(4, 'Kez'),
(5, 'Nelly'),
(6, 'Josese'),
(7, 'Blaise'),
(8, 'Elissa'),
(9, 'Lilia'),
(10, 'Majka'),
(11, 'Ayooluwa'),
(12, 'Dara'),
(13, 'Ellia'),
(14, 'Joash'),
(15, 'Jolie');

--
-- Indexes for dumped tables
--

--
-- Indexes for table `course`
--
ALTER TABLE `course`
  ADD PRIMARY KEY (`course_id`);

--
-- Indexes for table `member`
--
ALTER TABLE `member`
  ADD PRIMARY KEY (`user_id`,`course_id`),
  ADD KEY `course_id` (`course_id`);

--
-- Indexes for table `user`
--
ALTER TABLE `user`
  ADD PRIMARY KEY (`user_id`);

--
-- AUTO_INCREMENT for dumped tables
--

--
-- AUTO_INCREMENT for table `course`
--
ALTER TABLE `course`
  MODIFY `course_id` int(11) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=4;

--
-- AUTO_INCREMENT for table `user`
--
ALTER TABLE `user`
  MODIFY `user_id` int(11) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=16;

--
-- Constraints for dumped tables
--

--
-- Constraints for table `member`
--
ALTER TABLE `member`
  ADD CONSTRAINT `member_ibfk_1` FOREIGN KEY (`user_id`) REFERENCES `user` (`user_id`) ON DELETE CASCADE ON UPDATE CASCADE,
  ADD CONSTRAINT `member_ibfk_2` FOREIGN KEY (`course_id`) REFERENCES `course` (`course_id`) ON DELETE CASCADE ON UPDATE CASCADE;
--
-- Database: `school`
--
CREATE DATABASE IF NOT EXISTS `school` DEFAULT CHARACTER SET utf8 COLLATE utf8_general_ci;
USE `school`;

-- --------------------------------------------------------

--
-- Table structure for table `admission_rec`
--

CREATE TABLE `admission_rec` (
  `id` int(11) NOT NULL,
  `standard` int(11) DEFAULT NULL,
  `division` varchar(2) DEFAULT NULL,
  `age` float DEFAULT NULL,
  `address` varchar(50) DEFAULT NULL,
  `phone_no` int(11) DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8;

-- --------------------------------------------------------

--
-- Table structure for table `students`
--

CREATE TABLE `students` (
  `id` int(11) NOT NULL,
  `name` varchar(50) DEFAULT NULL,
  `standard` int(11) DEFAULT NULL,
  `division` varchar(2) DEFAULT NULL,
  `marks` float DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8;

--
-- Dumping data for table `students`
--

INSERT INTO `students` (`id`, `name`, `standard`, `division`, `marks`) VALUES
(1, 'rahul', 7, 'A', 98),
(2, 'priya', 9, 'B', 78);

--
-- Indexes for dumped tables
--

--
-- Indexes for table `admission_rec`
--
ALTER TABLE `admission_rec`
  ADD PRIMARY KEY (`id`);

--
-- Indexes for table `students`
--
ALTER TABLE `students`
  ADD PRIMARY KEY (`id`);
--
-- Database: `spit`
--
CREATE DATABASE IF NOT EXISTS `spit` DEFAULT CHARACTER SET utf8 COLLATE utf8_general_ci;
USE `spit`;

-- --------------------------------------------------------

--
-- Table structure for table `department`
--

CREATE TABLE `department` (
  `DNO` int(11) NOT NULL,
  `Dname` varchar(20) DEFAULT NULL,
  `mgrSSN` int(11) DEFAULT NULL,
  `mgrstartdate` date DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8;

--
-- Dumping data for table `department`
--

INSERT INTO `department` (`DNO`, `Dname`, `mgrSSN`, `mgrstartdate`) VALUES
(201, 'research', 201, '2020-09-19'),
(202, 'IT', 202, '2020-09-18'),
(203, 'COMPS', 203, '2020-09-19'),
(204, 'EXTC', 204, '2020-09-19'),
(205, 'ETRX', 205, '2020-09-19'),
(206, 'MECH', 206, '2020-09-19'),
(207, 'CHEM', 207, '2020-09-19');

-- --------------------------------------------------------

--
-- Table structure for table `dlocation`
--

CREATE TABLE `dlocation` (
  `DNO` int(11) DEFAULT NULL,
  `DLOC` varchar(50) DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8;

--
-- Dumping data for table `dlocation`
--

INSERT INTO `dlocation` (`DNO`, `DLOC`) VALUES
(201, 'ville,mumbai'),
(202, 'parle,mumbai'),
(203, 'santacruz,mumbai'),
(204, 'chembur,mumbai'),
(205, 'grant,mumbai'),
(206, 'road,mumbai'),
(207, 'ville,mumbai');

-- --------------------------------------------------------

--
-- Table structure for table `employee`
--

CREATE TABLE `employee` (
  `SSN` int(11) NOT NULL,
  `name` varchar(20) DEFAULT NULL,
  `address` varchar(50) DEFAULT NULL,
  `sex` varchar(1) DEFAULT NULL,
  `salary` int(11) DEFAULT NULL,
  `superSSN` int(11) DEFAULT NULL,
  `DNO` int(11) DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8;

--
-- Dumping data for table `employee`
--

INSERT INTO `employee` (`SSN`, `name`, `address`, `sex`, `salary`, `superSSN`, `DNO`) VALUES
(101, 'pankaj', 'parle,mumbai', 'M', 20000, 201, 201),
(102, 'kaustubh', 'ville,mumbai', 'F', 30000, 202, 202),
(103, 'yug', 'parle,mumbai', 'O', 20000, 203, 203),
(104, 'jai', 'andheri,mumbai', 'M', 40000, 204, 204),
(105, 'jash', 'BKC,mumbai', 'O', 20000, 204, 204),
(106, 'ramesh', 'oxford,mumbai', 'F', 50000, 204, 204),
(107, 'isha', 'pune,mumbai', 'M', 20000, 201, 201);

-- --------------------------------------------------------

--
-- Table structure for table `project`
--

CREATE TABLE `project` (
  `PNO` int(11) NOT NULL,
  `pname` varchar(20) DEFAULT NULL,
  `plocation` varchar(50) DEFAULT NULL,
  `DNO` int(11) DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8;

--
-- Dumping data for table `project`
--

INSERT INTO `project` (`PNO`, `pname`, `plocation`, `DNO`) VALUES
(301, 'reliance', 'mumbai', 201),
(302, 'morgan', 'pune', 202),
(303, 'wipro', 'mumbai', 204),
(304, 'kotak', 'delhi', 203),
(305, 'jio', 'chennai', 205),
(306, 'adani', 'kolkata', 205),
(307, 'reliance', 'mumbai', 207);

-- --------------------------------------------------------

--
-- Table structure for table `works_on`
--

CREATE TABLE `works_on` (
  `SSN` int(11) DEFAULT NULL,
  `PNO` int(11) DEFAULT NULL,
  `hours` float DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8;

--
-- Dumping data for table `works_on`
--

INSERT INTO `works_on` (`SSN`, `PNO`, `hours`) VALUES
(101, 301, 12),
(102, 302, 12),
(101, 303, 12),
(103, 305, 12),
(104, 305, 12),
(105, 304, 12),
(107, 306, 12);

--
-- Indexes for dumped tables
--

--
-- Indexes for table `department`
--
ALTER TABLE `department`
  ADD PRIMARY KEY (`DNO`);

--
-- Indexes for table `dlocation`
--
ALTER TABLE `dlocation`
  ADD KEY `dlocation_dno` (`DNO`);

--
-- Indexes for table `employee`
--
ALTER TABLE `employee`
  ADD PRIMARY KEY (`SSN`),
  ADD KEY `employee_dno` (`DNO`);

--
-- Indexes for table `project`
--
ALTER TABLE `project`
  ADD PRIMARY KEY (`PNO`),
  ADD KEY `project_dno` (`DNO`);

--
-- Indexes for table `works_on`
--
ALTER TABLE `works_on`
  ADD KEY `works_on_ssn` (`SSN`),
  ADD KEY `works_on_pno` (`PNO`);

--
-- Constraints for dumped tables
--

--
-- Constraints for table `dlocation`
--
ALTER TABLE `dlocation`
  ADD CONSTRAINT `dlocation_dno` FOREIGN KEY (`DNO`) REFERENCES `department` (`DNO`);

--
-- Constraints for table `employee`
--
ALTER TABLE `employee`
  ADD CONSTRAINT `employee_dno` FOREIGN KEY (`DNO`) REFERENCES `department` (`DNO`);

--
-- Constraints for table `project`
--
ALTER TABLE `project`
  ADD CONSTRAINT `project_dno` FOREIGN KEY (`DNO`) REFERENCES `department` (`DNO`);

--
-- Constraints for table `works_on`
--
ALTER TABLE `works_on`
  ADD CONSTRAINT `works_on_pno` FOREIGN KEY (`PNO`) REFERENCES `project` (`PNO`),
  ADD CONSTRAINT `works_on_ssn` FOREIGN KEY (`SSN`) REFERENCES `employee` (`SSN`);
COMMIT;

/*!40101 SET CHARACTER_SET_CLIENT=@OLD_CHARACTER_SET_CLIENT */;
/*!40101 SET CHARACTER_SET_RESULTS=@OLD_CHARACTER_SET_RESULTS */;
/*!40101 SET COLLATION_CONNECTION=@OLD_COLLATION_CONNECTION */;
