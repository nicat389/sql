-- phpMyAdmin SQL Dump
-- version 4.6.5.2
-- https://www.phpmyadmin.net/
--
-- Host: 127.0.0.1
-- Generation Time: Feb 11, 2017 at 12:50 PM
-- Server version: 10.1.21-MariaDB
-- PHP Version: 7.1.1

SET SQL_MODE = "NO_AUTO_VALUE_ON_ZERO";
SET time_zone = "+00:00";


/*!40101 SET @OLD_CHARACTER_SET_CLIENT=@@CHARACTER_SET_CLIENT */;
/*!40101 SET @OLD_CHARACTER_SET_RESULTS=@@CHARACTER_SET_RESULTS */;
/*!40101 SET @OLD_COLLATION_CONNECTION=@@COLLATION_CONNECTION */;
/*!40101 SET NAMES utf8mb4 */;

--
-- Database: `market`
--

-- --------------------------------------------------------

--
-- Table structure for table `alici`
--

CREATE TABLE `alici` (
  `id` int(11) NOT NULL,
  `name` varchar(50) DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=latin1;

--
-- Dumping data for table `alici`
--

INSERT INTO `alici` (`id`, `name`) VALUES
(1, 'Elvin'),
(2, 'Isgender'),
(3, 'Nicat'),
(4, 'Rashad'),
(5, 'Xeyal'),
(6, 'Ismayil'),
(7, 'Seid');

-- --------------------------------------------------------

--
-- Table structure for table `ishci`
--

CREATE TABLE `ishci` (
  `id` int(11) NOT NULL,
  `name` varchar(50) DEFAULT NULL,
  `maash` int(11) DEFAULT NULL,
  `elave_maash` int(11) DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=latin1;

--
-- Dumping data for table `ishci`
--

INSERT INTO `ishci` (`id`, `name`, `maash`, `elave_maash`) VALUES
(1, 'Hesen', 500, NULL),
(2, 'Huseyn', 600, NULL),
(3, 'Lale', 700, NULL),
(4, 'Elvin', 800, NULL),
(5, 'Fariz', 100, NULL);

-- --------------------------------------------------------

--
-- Table structure for table `mallar`
--

CREATE TABLE `mallar` (
  `id` int(11) NOT NULL,
  `malin_adi` varchar(50) DEFAULT NULL,
  `qiymeti` int(11) DEFAULT NULL,
  `seksiya` int(11) DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=latin1;

--
-- Dumping data for table `mallar`
--

INSERT INTO `mallar` (`id`, `malin_adi`, `qiymeti`, `seksiya`) VALUES
(1, 'Alma', 2, 1),
(2, 'Apelsin', 3, 1),
(3, 'Shaftali', 5, 1),
(4, 'Kivi', 3, 1),
(5, 'Banan', 5, 1),
(6, 'Cola', 1, 2),
(7, 'Sprite', 1, 2),
(8, 'Kofe', 1, 2),
(9, 'Jale', 4, 2),
(10, 'Qazli', 1, 2),
(11, 'Cake', 3, 4),
(12, 'Qogal', 1, 4),
(13, 'Xachapuri', 1, 4),
(14, 'Shekerbura', 1, 4),
(15, 'Bulka', 2, 4),
(16, 'Telefon', 1, 3),
(17, 'Kabel', 2, 3),
(18, 'Avterka', 2, 3),
(19, 'Shurup', 2, 3),
(20, 'Shayba', 4, 3),
(21, 'Tekish', 6, 3);

-- --------------------------------------------------------

--
-- Table structure for table `seksiya`
--

CREATE TABLE `seksiya` (
  `id` int(11) NOT NULL,
  `ad` varchar(50) DEFAULT NULL,
  `ishci_id` int(11) DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=latin1;

--
-- Dumping data for table `seksiya`
--

INSERT INTO `seksiya` (`id`, `ad`, `ishci_id`) VALUES
(1, 'Meyve_terevez', 1),
(2, 'Ichkiler', 1),
(3, 'Texnika', 3),
(4, 'Shirniyyat', 4),
(5, 'Meishet', NULL);

-- --------------------------------------------------------

--
-- Table structure for table `sifarish`
--

CREATE TABLE `sifarish` (
  `id` int(11) NOT NULL,
  `aldigi_mal` int(11) DEFAULT NULL,
  `alici` int(11) DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=latin1;

--
-- Dumping data for table `sifarish`
--

INSERT INTO `sifarish` (`id`, `aldigi_mal`, `alici`) VALUES
(1, 1, 1),
(2, 2, 1),
(3, 3, 1),
(4, 4, 1),
(5, 5, 1),
(6, 9, 2),
(7, 10, 2),
(8, 11, 2),
(9, 15, 3),
(10, 14, 3),
(11, 16, 2),
(12, 17, 2),
(13, 18, 2),
(14, 19, 2),
(15, 20, 2),
(16, 21, 2);

--
-- Indexes for dumped tables
--

--
-- Indexes for table `alici`
--
ALTER TABLE `alici`
  ADD PRIMARY KEY (`id`);

--
-- Indexes for table `ishci`
--
ALTER TABLE `ishci`
  ADD PRIMARY KEY (`id`);

--
-- Indexes for table `mallar`
--
ALTER TABLE `mallar`
  ADD PRIMARY KEY (`id`),
  ADD KEY `seksiya` (`seksiya`);

--
-- Indexes for table `seksiya`
--
ALTER TABLE `seksiya`
  ADD PRIMARY KEY (`id`),
  ADD KEY `ishci_id` (`ishci_id`);

--
-- Indexes for table `sifarish`
--
ALTER TABLE `sifarish`
  ADD PRIMARY KEY (`id`),
  ADD KEY `aldigi_mal` (`aldigi_mal`),
  ADD KEY `alici` (`alici`);

--
-- AUTO_INCREMENT for dumped tables
--

--
-- AUTO_INCREMENT for table `alici`
--
ALTER TABLE `alici`
  MODIFY `id` int(11) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=8;
--
-- AUTO_INCREMENT for table `ishci`
--
ALTER TABLE `ishci`
  MODIFY `id` int(11) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=6;
--
-- AUTO_INCREMENT for table `mallar`
--
ALTER TABLE `mallar`
  MODIFY `id` int(11) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=22;
--
-- AUTO_INCREMENT for table `seksiya`
--
ALTER TABLE `seksiya`
  MODIFY `id` int(11) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=6;
--
-- AUTO_INCREMENT for table `sifarish`
--
ALTER TABLE `sifarish`
  MODIFY `id` int(11) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=17;
--
-- Constraints for dumped tables
--

--
-- Constraints for table `mallar`
--
ALTER TABLE `mallar`
  ADD CONSTRAINT `mallar_ibfk_1` FOREIGN KEY (`seksiya`) REFERENCES `seksiya` (`id`) ON DELETE CASCADE ON UPDATE CASCADE;

--
-- Constraints for table `seksiya`
--
ALTER TABLE `seksiya`
  ADD CONSTRAINT `seksiya_ibfk_1` FOREIGN KEY (`ishci_id`) REFERENCES `ishci` (`id`) ON DELETE CASCADE ON UPDATE CASCADE;

--
-- Constraints for table `sifarish`
--
ALTER TABLE `sifarish`
  ADD CONSTRAINT `sifarish_ibfk_2` FOREIGN KEY (`aldigi_mal`) REFERENCES `mallar` (`id`) ON DELETE CASCADE ON UPDATE CASCADE,
  ADD CONSTRAINT `sifarish_ibfk_3` FOREIGN KEY (`alici`) REFERENCES `alici` (`id`) ON DELETE CASCADE ON UPDATE CASCADE;

/*!40101 SET CHARACTER_SET_CLIENT=@OLD_CHARACTER_SET_CLIENT */;
/*!40101 SET CHARACTER_SET_RESULTS=@OLD_CHARACTER_SET_RESULTS */;
/*!40101 SET COLLATION_CONNECTION=@OLD_COLLATION_CONNECTION */;
